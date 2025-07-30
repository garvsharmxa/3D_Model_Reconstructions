# 3Dify: Image to 3D Human Model Reconstruction

![PIFuHD Demo](https://shunsukesaito.github.io/PIFuHD/resources/images/pifuhd.gif)

A Google Colab implementation for converting 2D human images into detailed 3D models using PIFuHD (Pixel-Aligned Implicit Function for High-Resolution Clothed Human Digitization).

**Enhanced by**: [Garv Sharma](https://github.com/garvsharmxa/) with additional features for improved usability and accessibility.

## 🚀 Features

- **2D to 3D Conversion**: Transform single human images into detailed 3D mesh models
- **High-Resolution Output**: Generate 3D models with fine clothing and surface details
- **Multiple Input Methods**: Support for both internet URLs and local file uploads *(Enhanced Feature)*
- **Complete Pipeline**: Includes pose estimation, 3D reconstruction, and video rendering
- **Ready-to-Use**: Pre-configured Google Colab environment with all dependencies
- **URL Image Processing**: Direct image processing from web URLs *(New Addition)*
- **Enhanced Error Handling**: Improved debugging and troubleshooting capabilities
- **Automated Downloads**: Streamlined result downloading with file verification

## 📋 Requirements

### Hardware
- **GPU Required**: Google Colab with GPU acceleration enabled
- **Runtime**: Python 3 with GPU acceleration

### Software Dependencies
- Python 3
- PyTorch 2.4.1
- TorchVision 0.19.1
- PyTorch3D
- OpenCV (cv2)
- NumPy
- PIL/Pillow
- scikit-image
- IPython

## 🛠️ Installation & Setup

### Google Colab Setup
1. Open the notebook in Google Colab
2. **Important**: Set runtime to GPU
   - Go to `Edit` → `Notebook settings` → `Hardware Accelerator` → Select `GPU`
3. Run the setup cell to install all dependencies

### Local Setup (Advanced Users)
```bash
# Clone repositories
git clone https://github.com/facebookresearch/pifuhd
git clone https://github.com/Daniil-Osokin/lightweight-human-pose-estimation.pytorch.git

# Install PyTorch and dependencies
pip install torch==2.4.1 torchvision==0.19.1
pip install git+https://github.com/facebookresearch/pytorch3d.git

# Download pre-trained models
cd pifuhd
sh ./scripts/download_trained_model.sh
```

## 🚀 Quick Start

### Method 1: Using Internet Images *(Enhanced Feature)*
1. Run the setup cell (STEP 1)
2. Use the "Uploading Image From Internet" section
3. Paste an image URL in the `image_url` field
4. The system will automatically download and process the image from the URL
5. Execute the cell to process the image
6. Download results using the download cell

**Note**: This feature allows you to process images directly from the web without manual downloading. Simply copy any image URL and paste it in the designated field.

### Method 2: Using Local Images
1. Run the setup cell (STEP 1)
2. Use the "Upload Image From Local Desktop" section
3. Upload your image file when prompted
4. The processing will start automatically
5. Download results using the download cell

## 📁 Output Files

The system generates several output files:

- **`.obj` file**: 3D mesh model (importable to Blender, Maya, etc.)
- **`.png` file**: Rendered 2D view of the 3D model
- **`.mp4` file**: 360° rotation video of the 3D model

## 🎯 Best Practices for Input Images

### Ideal Image Characteristics
- **Human Subject**: Single person clearly visible
- **Full Body**: Complete human figure preferred
- **Clear Pose**: Person should be standing upright
- **Good Lighting**: Even lighting without harsh shadows
- **Minimal Occlusion**: Avoid objects blocking the person
- **High Resolution**: Higher resolution images yield better results

### Supported Formats
- JPEG (.jpg, .jpeg)
- PNG (.png)
- BMP (.bmp)
- TIFF (.tiff)

## 🔧 Technical Details

### Pipeline Overview
1. **Pose Estimation**: Uses Lightweight Human Pose Estimation to detect human keypoints
2. **Bounding Box Generation**: Creates optimal crop regions around detected humans
3. **3D Reconstruction**: PIFuHD generates detailed 3D mesh from 2D image
4. **Post-Processing**: Renders final outputs and creates visualization videos

### Model Information
- **PIFuHD**: Facebook Research's state-of-the-art implicit function approach
- **Resolution**: Maximum 256x256 on Google Colab (higher resolutions require more VRAM)
- **Processing Time**: Typically 2-5 minutes per image on Colab GPU

## 📊 Performance & Limitations

### System Limitations
- **Resolution Cap**: 256x256 maximum on Google Colab
- **Single Person**: Works best with single human subjects
- **Pose Requirements**: Standing poses work better than sitting/lying
- **GPU Memory**: Limited by Colab's GPU memory allocation

### Performance Tips
- Use high-quality input images
- Ensure person is clearly visible and well-lit
- Avoid complex backgrounds when possible
- Standing/walking poses generally work better

## 🔍 Troubleshooting

### Common Issues

**Issue**: "No pose detected"
- **Solution**: Ensure the image contains a clearly visible human figure
- Check image quality and lighting

**Issue**: "GPU out of memory"
- **Solution**: Restart runtime and try again
- Use smaller input images

**Issue**: "Download files not found"
- **Solution**: Wait for processing to complete
- Check if pose estimation step succeeded

**Issue**: "Checkpoint download failed"
- **Solution**: Check internet connection
- Try running setup cell again

### Debug Information
The notebook includes comprehensive error checking and will provide detailed information about any processing failures.

## 📚 Additional Resources

### 3D Model Viewers
- **Blender** (Free): Professional 3D modeling software
- **MeshLab** (Free): 3D mesh processing tool
- **3D Viewer** (Windows): Built-in Windows 10/11 viewer
- **Online Viewers**: ViewSTL, Sketchfab, etc.

### Research Papers
- [PIFuHD: Multi-Level Pixel-Aligned Implicit Function for High-Resolution 3D Human Digitization](https://shunsukesaito.github.io/PIFuHD/)
- [PIFu: Pixel-Aligned Implicit Function for High-Resolution Clothed Human Digitization](https://shunsukesaito.github.io/PIFu/)

## 🤝 Contributing

This project is based on research work from Facebook Research and other contributors. For improvements or issues:

1. Check existing issues in the original repositories
2. Contribute to the underlying research projects
3. Share your results and improvements

## 📄 License

This project uses components from multiple sources:
- PIFuHD: Facebook Research
- Lightweight Human Pose Estimation: Intel
- Various Python packages under their respective licenses

Please refer to individual component licenses for detailed terms.

## 🙏 Acknowledgments

- **Facebook Research** for PIFuHD
- **Intel** for Lightweight Human Pose Estimation
- **PyTorch3D** team for 3D processing utilities
- **Google Colab** for providing accessible GPU computing

## 👨‍💻 Enhanced Implementation

**Developed and Enhanced by**: [Garv Sharma](https://github.com/garvsharmxa/)

### Key Enhancements Added:
- **Internet URL Image Processing**: Added capability to process images directly from web URLs without manual downloading
- **Improved Error Handling**: Enhanced debugging and error reporting for better user experience
- **Streamlined Workflow**: Simplified the process with automated file management and processing
- **Enhanced Download System**: Improved result downloading with comprehensive file verification
- **Better Documentation**: Added detailed troubleshooting and user guidance

### Original Research References:
- **PIFuHD Method**: [Multi-Level Pixel-Aligned Implicit Function for High-Resolution 3D Human Digitization](https://shunsukesaito.github.io/PIFuHD/)
- **Background Removal Tool**: [Remove.bg](https://www.remove.bg/) for preprocessing images

## 📞 Support

For technical issues:
1. Check the troubleshooting section above
2. Review the original research papers
3. Consult the underlying project repositories

---

**Note**: This is a research tool intended for educational and experimental purposes. Results may vary based on input image quality and computational resources.
