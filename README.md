# AMD AMF Encoding test

Encoding test for OBS (https://obsproject.com/)

Encoders tested: 
1. x264 (for baseline)
2. H264/AVC Encoder (AMD Advanced Media Framework) (included in base OBS)
3. AMF AVC GPU (plugin from https://github.com/e00E/obs-amf/releases)
4. AMD AMF H.264/AVC (via FFmpeg) (included with https://github.com/Xaymar/obs-StreamFX/releases)

Testing method:
1. Recorded lossless 2560x1440 60fps gameplay footage using OBS - reference file for test
2. Set the lossless reference file as a VLC media source in a new OBS scene
3. Set output as 2560x1440 60fps (no scaling)
4. Target bitrate as 13k - I want to test
5. Recorded the footage using various configs of encoders
6. Trimmed footage to have same start and end frames
7. Compared with FFmetrics GUI (https://github.com/fifonik/FFMetrics/releases)

Video files for the test: TODO

Detailed Results - Results.csv

Due to limited performance of my CPU i5 10400, I could not encode on x264 above veryfast at any usable bitrate.

Conclusion:

For 1440p60 stream at 13k bitrate the encoders are ranked as follows
x264 > AMF AVC GPU > H264/AVC Encoder (AMD Advanced Media Framework) > AMD AMF H.264/AVC (via FFmpeg)
