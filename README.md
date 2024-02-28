# Creation-of-Gif-
from PIL import Image, ImageDraw

# Create a list of images
images = []

# Create frames
for i in range(10):
    # Create a new image with a white background
    img = Image.new('RGB', (200, 200), color=(255, 255, 255))
    
    # Draw on the image
    d = ImageDraw.Draw(img)
    d.text((20, 20), f"Frame {i}", fill=(0, 0, 0))
    
    # Append the image to the list
    images.append(img)

# Save the frames as a GIF
images[0].save('example.gif',
               save_all=True,
               append_images=images[1:],
               duration=100,
               loop=0)
