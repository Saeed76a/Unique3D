**中文版本 [中文](README_zh.md)**

# Unique3D
High-Quality and Efficient 3D Mesh Generation from a Single Image

## [Paper]() | [Project page](https://wukailu.github.io/Unique3D/) | [Huggingface Demo]() | [Online Demo](https://www.aiuni.ai/)

![](assets/fig_teaser.png)

High-fidelity and diverse textured meshes generated by Unique3D from single-view wild images in 30 seconds.

## More features 

The repo is still being under construction, thanks for your patience. 
- [x] Local gradio demo.
- [ ] Detailed tutorial.
- [ ] Huggingface demo.
- [ ] Detailed local demo.
- [ ] Comfyui support.
- [ ] Windows support.
- [ ] Docker support.
- [ ] More stable reconstruction with normal.
- [ ] Training code release.

## Preparation for inference

### Linux System Setup.
```angular2html
conda create -n unique3d
conda activate unique3d
pip install -r requirements.txt
```

### Interactive inference: run your local gradio demo.

1. Download the [ckpt.zip](), and extract it to `ckpt/*`.
```
Unique3D
    ├──ckpt
        ├── controlnet-tile/
        ├── image2normal/
        ├── img2mvimg/
        ├── realesrgan-x4.onnx
        └── v1-inference.yaml
```

2. Run the interactive inference locally.
```bash
python app/gradio_local.py --port 7860
```

## Tips to get better results

1. Unique3D is sensitive to the facing direction of input images. Due to the distribution of the training data, orthographic front-facing images with a rest pose always lead to good reconstructions.
2. Images with occlusions will cause worse reconstructions, since four views cannot cover the complete object. Images with fewer occlusions lead to better results.
3. Pass an image with as high a resolution as possible to the input when resolution is a factor.

## Acknowledgement

We have intensively borrowed code from the following repositories. Many thanks to the authors for sharing their code.
- [Stable Diffusion](https://github.com/CompVis/stable-diffusion)
- [Wonder3d](https://github.com/xxlong0/Wonder3D)
- [Zero123Plus](https://github.com/SUDO-AI-3D/zero123plus)
- [Continues Remeshing](https://github.com/Profactor/continuous-remeshing)
- [Depth from Normals](https://github.com/YertleTurtleGit/depth-from-normals)

## Collaborations
Our mission is to create a 4D generative model with 3D concepts. This is just our first step, and the road ahead is still long, but we are confident. We warmly invite you to join the discussion and explore potential collaborations in any capacity. <span style="color:red">**If you're interested in connecting or partnering with us, please don't hesitate to reach out via email (wkl22@mails.tsinghua.edu.cn)**</span>.