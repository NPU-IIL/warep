# warep
一个通用的EEG处理工具库

## 大纲

* Preprocess
* FeatureExtraction
  * time domain
  * frequency domain
  * space domain
* DeepLearningModel
* PlotUtils

## 编写规范

### 命名规范

#### 类名

* 总是使用首字母大写单词串，并使用驼峰命名法

#### 函数命名

* 全部小写，如有多个单词，用_下划线隔开，私有函数可用前导下划线,例如

```
def compute_power_spectral_density()
```

#### 变量命名

* 变量名一般小写，多个单词用_下划线隔开
* 全局变量全部大写，多个单词用_下划线隔开

#### 常用约定变量

例如：

fs：采样率

data：二维eeg信号Channel*Samples

band：频带，例如[1,4,8,13,31,70],表示5个频带

### 注释规范

```
    """
    Introduction:
        对函数或类主要用法进行介绍
    Args:
        参数介绍，包括数据类型
    Returns:
        返回值说明，包括数据类型
    Examples：
    """
```
例如：
```
def ica_eeg(data,fs):
    """
    Introduction:
        对eeg信号进行ICA去伪迹
    Args:
        data:channels * samples EEG data
        fs: sampling rates, Default: 250
    Returns:
        icaed_data:ICA处理过的EEG数据 channels * samples
    Examples：
    	>>> inputs = torch.randn(8, 300)
    	>>> fs = 250
    	>>> icaed_data = ica_eeg(inputs,fs)
    """
```
