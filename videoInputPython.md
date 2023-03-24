# vidioInputPython
//Program inputs any video and display a output video which skips 75% of the frames.
import cv2

# Open the input video file
input_video = cv2.VideoCapture('input_video.mp4')

# Get the video properties
frame_count = int(input_video.get(cv2.CAP_PROP_FRAME_COUNT))
frame_width = int(input_video.get(cv2.CAP_PROP_FRAME_WIDTH))
frame_height = int(input_video.get(cv2.CAP_PROP_FRAME_HEIGHT))
fps = int(input_video.get(cv2.CAP_PROP_FPS))

# Create the output video writer
fourcc = cv2.VideoWriter_fourcc(*'mp4v')
output_video = cv2.VideoWriter('output_video.mp4', fourcc, fps, (frame_width, frame_height))

# Process the frames and write to the output video
skip_frame_count = 3  # skip 75% of the frames (3 out of 4)
frame_index = 0
while True:
    ret, frame = input_video.read()
    if not ret:
        break
    if frame_index % skip_frame_count == 0:
        output_video.write(frame)
    frame_index += 1

# Release the video objects
input_video.release()
output_video.release()
