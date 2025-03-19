# ComfyUI Workflows

This project contains three ComfyUI workflows designed to perform face swapping in various contexts: image-to-image replacement, video frame-by-frame swapping, and face model creation.

--- 

## Workflow Descriptions

### 1. FaceModelMaker_v1.json

![image](https://github.com/user-attachments/assets/97803021-a0a8-4226-b183-b48e6eb55a35)

#### Purpose:
This workflow is used to create a face model from a batch of input images. The generated face model can be used for face swapping tasks.

#### Components:
- **LoadImage Nodes:** Loads multiple images to be used for face model creation.
- **Make Image Batch Nodes:** Combines loaded images into batches.
- **ReActorBuildFaceModel Nodes:** Builds the face model using the provided image batches.
- **PreviewImage Node:** Previews generated images.
- **ReActorSaveFaceModel Nodes:** Saves the generated face models into files for future use.

### 2. PicSwapper_v1.json

![image](https://github.com/user-attachments/assets/87b118cf-6afa-4c3a-aeed-f7a5684f2b61)

#### Purpose:
This workflow applies face swapping to static images using a pre-trained face model, it is intended to be used as integration into antoher more complex workflow, not as is. 

#### Components:
- **ReActorLoadFaceModel Node:** Loads a pre-trained face model.
- **LoadImage Node:** Loads the source image from which the face will be swapped.
- **ReActorFaceSwap Node:** Performs the face swap operation on the source image with the loaded face model.
- **SaveImage Node:** Saves the face-swapped image.

### 3. VidSwapper_v1.json

![image](https://github.com/user-attachments/assets/0d09cfeb-b966-48ad-bbac-98439f248e3f)

#### Purpose:
This workflow performs face swapping on each frame of a video. Possibility of enabling frame interpolation to artificially augment ips. 

#### Components:
- **LoadVideo Node:** Loads a video file and extracts frames.
- **ReActorLoadFaceModel Node:** Loads a face model for use in swapping.
- **ReActorFaceSwap Node:** Swaps faces on each extracted frame using the loaded face model.
- **FrameInterpolator Node:** Interpolates frames between the swaps if needed.
- **SaveVideo Node:** Compiles the frames back into a video and saves it.

--- 

## Usage

To use these workflows, you need to have ComfyUI installed and configure it to load these JSON files.
- Load each workflow as needed depending on whether you want to create a face model, perform single image swaps, or work on video files.
- Ensure that the paths to source images, face models, and videos are correctly set in the widget values within the workflow nodes.

## Notes
- Ensure enough computational resources are available, especially for video processing.
- Verify file paths and model names are correct to avoid errors during execution.
- Adjust widget values in nodes like face boost settings according to the visual quality desired.

These workflows are designed to streamline the process of face swapping using ComfyUI, enabling efficient and automated model creation and application across different media.

---

**Disclaimer:** 
This workflow is provided "as-is" without any warranties. 
The user assumes all responsibility for compliance with applicable laws and regulations. 
The creators are not liable for any misuse or consequences arising from its use.

---

ReadMe automatically generated with AI
