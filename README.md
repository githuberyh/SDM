# SDM

Converting Artificial Neural Networks to Ultra-Low-Latency Spiking Neural Networks for Action Recognition<br />
Hong You, Xian Zhong, Wenxuan Liu, Qi Wei, Wenxin Huang, Zhaofei Yu, Tiejun Huang.

## Dataset

~~~
|UCF-101
    |annotations
        |classInd.txt
        |trainlist.txt
        |testlist.txt
    |videos
    |ucf101_train_split_videos.txt
    |ucf101_test_split_videos.txt`
~~~

## Training
Run the following commands:

~~~python
python tools/train.py configs/recognition/slowfast/my_slowfast_r50_4x16x1_256e_ucf101_rgb.py --work-dir work_dirs/myspikingslowfast_clamp_bs8_r50_video_4x16x1_256e_ucf101_rgb --validate --seed 0 --deterministic
~~~


## Testing
Run the following commands: 
~~~python
python tools/test.py configs/recognition/slowfast/my_slowfast_r50_4x16x1_256e_ucf101_rgb.py work_dirs/myspikingslowfast_clamp_r50_video_4x16x1_256e_ucf101_rgb/sdop_init1_epoch_40.pth --eval top_k_accuracy --T 8

~~~

