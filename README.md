# P3AR-NTU

This repository provides the processing scripts and metadata for the **P3AR-NTU** dataset introduced in:

**Lens Privacy Sealing: A New Benchmark and Method for Physical Privacy-Preserving Action Recognition**  
Mengyuan Liu, Ziyi Wang<sup>&dagger;</sup>, Peiming Li<sup>&dagger;</sup>, Junsong Yuan  
Accepted as a Regular Paper by **IEEE Transactions on Image Processing (T-IP)**.

<sup>&dagger;</sup> Corresponding authors: Ziyi Wang and Peiming Li.

## Overview

P3AR-NTU is the large-scale replay-and-capture subset of the P3AR benchmark for physical privacy-preserving action recognition. It is constructed from NTU RGB+D 120 by physically recapturing the original videos with a camera covered by Lens Privacy Sealing (LPS), a low-cost laminating-film privacy mask. The resulting videos preserve action cues while suppressing privacy-sensitive visual details.

This repository contains scripts used to organize the recaptured stream into NTU-style video samples. The companion MSPNet code repository is available at:

```text
https://github.com/wangzy01/MSPNet
```

## Download

Download the P3AR-NTU data from:

```text
https://pan.baidu.com/s/1BcO7uwanPu-1msp7o1gl3Q?pwd=l3tb
Access code: l3tb
```

The original NTU RGB+D 120 dataset should be obtained separately from the official NTU RGB+D release. It is used to recover sample names and frame ranges for alignment.

## Files

- `output_v2.txt`: precomputed mapping from start frame, end frame, and NTU sample name.
- `get_output_txt.py`: extracts sample frame ranges from the original NTU RGB+D 120 videos.
- `get_all_frames.py`: extracts frames from the recaptured raw video stream.
- `folders_for_each_video.py`: organizes extracted frames into one folder per video sample using `output_v2.txt`.
- `split_into_videos.py`: optionally splits the recaptured raw video into individual clips.
- `time.txt`: timing metadata from the original processing.

## Processing Steps

Before running the scripts, update the hard-coded paths in each Python file to match your local dataset locations.

1. Download P3AR-NTU from the link above.
2. Download the original NTU RGB+D 120 dataset separately.
3. If `output_v2.txt` is unavailable or needs to be regenerated, run:

```bash
python get_output_txt.py
```

4. Extract frames from the recaptured raw video stream:

```bash
python get_all_frames.py
```

5. Organize frames into per-sample folders:

```bash
python folders_for_each_video.py
```

6. Optionally split the raw recaptured video into separate video clips:

```bash
python split_into_videos.py
```

## Citation

```bibtex
@article{liu2026lens,
  title={Lens Privacy Sealing: A New Benchmark and Method for Physical Privacy-Preserving Action Recognition},
  author={Liu, Mengyuan and Wang, Ziyi and Li, Peiming and Yuan, Junsong},
  journal={IEEE Transactions on Image Processing},
  year={2026},
  note={Accepted}
}
```

## Contact

For questions about P3AR-NTU, please contact the corresponding authors:  
`ziyiwang@stu.pku.edu.cn`, `lipeiming1001@stu.pku.edu.cn`.

## License

This project is released under the MIT License. See [LICENSE](./LICENSE) for details.
