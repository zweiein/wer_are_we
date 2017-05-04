# wer_are_we
WER are we? An attempt at tracking states of the art(s) and recent results on speech recognition. *Feel free to correct!* 
(Inspired by [Are we there yet?](http://rodrigob.github.io/are_we_there_yet/build/))

To be updated with Interspeech 2015...

## WER

### LibriSpeech

(Possibly trained on more data than LibriSpeech.)

| WER test-clean | WER test-other | Paper          | Published | Notes   |
| :------------- | :------------- | :------------- | :-------- | :-----: |
| 5.83% | 12.69 | [Deep Speech 2: End-to-End Speech Recognition in English and Mandarin](http://arxiv.org/abs/1512.02595v1) | December 2015 | *Humans* |
| 4.28% | | [Purely sequence-trained neural networks for ASR based on lattice-free MMI](http://www.danielpovey.com/files/2016_interspeech_mmi.pdf) | September 2016 | HMM-TDNN trained with MMI + data augmentation (speed) + iVectors + 3 regularizations |
| 4.83% | | [A time delay neural network architecture for efficient modeling of long temporal contexts](http://speak.clsp.jhu.edu/uploads/publications/papers/1048_pdf.pdf) | 2015 | HMM-TDNN + iVectors |
| 5.33% | 13.25% | [Deep Speech 2: End-to-End Speech Recognition in English and Mandarin](http://arxiv.org/abs/1512.02595v1) | December 2015 | 9-layer model w/ 2 layers of 2D-invariant convolution & 7 recurrent layers, w/ 68M parameters trained on 11940h |
| 5.51% | 13.97% | [LibriSpeech: an ASR Corpus Based on Public Domain Audio Books](http://www.danielpovey.com/files/2015_icassp_librispeech.pdf) | 2015 | HMM-DNN + pNorm[*](http://www.danielpovey.com/files/2014_icassp_dnn.pdf) |
| 8.01% | 22.49% | same, [Kaldi](http://kaldi-asr.org/) | 2015 | HMM-(SAT)GMM |
| | 12.51% | [Audio Augmentation for Speech Recognition](http://www.danielpovey.com/files/2015_interspeech_augmentation.pdf) | 2015 | TDNN + pNorm + speed up/down speech |


### WSJ

(Possibly trained on more data than WSJ.)

| WER eval'92    | WER eval'93    | Paper          | Published | Notes   |
| :------------- | :------------- | :------------- | :-------- | :-----: |
| 3.47% | | [Deep Recurrent Neural Networks for Acoustic Modelling](http://arxiv.org/pdf/1504.01482v1.pdf) | April 2015 | TC-DNN-BLSTM-DNN |
| 5.03% | 8.08% | [Deep Speech 2: End-to-End Speech Recognition in English and Mandarin](http://arxiv.org/abs/1512.02595v1) | December 2015 | *Humans* |
| 3.63% | 5.66% | [LibriSpeech: an ASR Corpus Based on Public Domain Audio Books](http://www.danielpovey.com/files/2015_icassp_librispeech.pdf) | 2015 | test-set on open vocabulary (i.e. harder), model = HMM-DNN + pNorm[*](http://www.danielpovey.com/files/2014_icassp_dnn.pdf) |
| 3.60% | 4.98% | [Deep Speech 2: End-to-End Speech Recognition in English and Mandarin](http://arxiv.org/abs/1512.02595v1) | December 2015 | 9-layer model w/ 2 layers of 2D-invariant convolution & 7 recurrent layers, w/ 68M parameters |
| 5.6% | | [Convolutional Neural Networks-based Continuous Speech Recognition using Raw Speech Signal](http://infoscience.epfl.ch/record/203464/files/Palaz_Idiap-RR-18-2014.pdf) | 2014 | CNN over RAW speech (wav) |

### Switchboard Hub5'00

(Possibly trained on more data than SWB, but test set = full Hub5'00.)

| WER (SWB) | WER (full=SWB+CH) | Paper          | Published | Notes   |
| :-------  | :---------------- | :------------- | :-------- | :-----: |
| 5.5% | 10.3% | [English Conversational Telephone Speech Recognition by Humans and Machines](https://arxiv.org/pdf/1703.02136.pdf) | March 2017 | ResNet + BiLSTMs acoustic model, with 40d FMLLR + i-Vector inputs, trained on SWB+Fisher+CH, n-gram + model-M + LSTM + Strided (à trous) convs-based LM trained on Switchboard+Fisher+Gigaword+Broadcast |
| 6.3% | 11.9% | [The Microsoft 2016 Conversational Speech Recognition System](http://arxiv.org/pdf/1609.03528v1.pdf) | September 2016 | VGG/Resnet/LACE/BiLSTM acoustic model trained on SWB+Fisher+CH, N-gram + RNNLM language model trained on Switchboard+Fisher+Gigaword+Broadcast |
| 6.6% | 12.2% | [The IBM 2016 English Conversational Telephone Speech Recognition System](http://arxiv.org/pdf/1604.08242v2.pdf) | June 2016 | RNN + VGG + LSTM acoustic model trained on SWB+Fisher+CH, N-gram + "model M" + NNLM language model |
| 8.5% | 13% | [Purely sequence-trained neural networks for ASR based on lattice-free MMI](http://www.danielpovey.com/files/2016_interspeech_mmi.pdf) | September 2016 | HMM-BLSTM trained with MMI + data augmentation (speed) + iVectors + 3 regularizations + Fisher |
| 9.2% | 13.3% | [Purely sequence-trained neural networks for ASR based on lattice-free MMI](http://www.danielpovey.com/files/2016_interspeech_mmi.pdf) | September 2016 | HMM-TDNN trained with MMI + data augmentation (speed) + iVectors + 3 regularizations + Fisher (10% / 15.1% respectively trained on SWBD only) |
| 12.6% | 16% | [Deep Speech: Scaling up end-to-end speech recognition](http://arxiv.org/abs/1412.5567) | December 2014 | CNN + Bi-RNN + CTC (speech to letters), 25.9% WER if trained _only_ on SWB |
| 11% | 17.1% | [A time delay neural network architecture for efficient modeling of long temporal contexts](http://speak.clsp.jhu.edu/uploads/publications/papers/1048_pdf.pdf) | 2015 | HMM-TDNN + iVectors |
| 12.6% | 18.4% | [Sequence-discriminative training of deep neural networks](http://www.danielpovey.com/files/2013_interspeech_dnn.pdf) | 2013 | HMM-DNN +sMBR |
| 12.9% | 19.3% | [Audio Augmentation for Speech Recognition](http://www.danielpovey.com/files/2015_interspeech_augmentation.pdf) | 2015 | HMM-TDNN + pNorm + speed up/down speech |
| 15% | 19.1% | [Building DNN Acoustic Models for Large Vocabulary Speech Recognition](http://arxiv.org/abs/1406.7806v2) | June 2014  | DNN + Dropout |
| 10.4% | | [Joint Training of Convolutional and Non-Convolutional Neural Networks](http://www.mirlab.org/conference_papers/International_Conference/ICASSP%202014/papers/p5609-soltau.pdf) | 2014 | CNN on MFSC/fbanks + 1 non-conv layer for FMLLR/I-Vectors concatenated in a DNN |
| 11.5% | | [Deep Convolutional Neural Networks for LVCSR](http://www.cs.toronto.edu/~asamir/papers/icassp13_cnn.pdf) | 2013 | CNN |
| 12.2% | | [Very Deep Multilingual Convolutional Neural Networks for LVCSR](http://arxiv.org/pdf/1509.08967v1.pdf) | September 2015 | Deep CNN (10 conv, 4 FC layers), multi-scale feature maps |


### Fisher
(RT03S FSH)

| WER  | Paper          | Published | Notes   |
| :------ | :----- | :----- | :-----: |
| 9.6% | [Purely sequence-trained neural networks for ASR based on lattice-free MMI](http://www.danielpovey.com/files/2016_interspeech_mmi.pdf) | September 2016 | HMM-*BLSTM* trained with MMI + data augmentation (speed) + iVectors + 3 regularizations + SWBD |
| 9.8% | [Purely sequence-trained neural networks for ASR based on lattice-free MMI](http://www.danielpovey.com/files/2016_interspeech_mmi.pdf) | September 2016 | HMM-*TDNN* trained with MMI + data augmentation (speed) + iVectors + 3 regularizations + SWBD |

### CHiME (noisy speech)

| clean | real | sim | Paper | Published | Notes |
| :------ | :----- | :----- | :----- | :----- | :-----: |
| 3.34% | 21.79% | 45.05% | [Deep Speech 2: End-to-End Speech Recognition in English and Mandarin](http://arxiv.org/abs/1512.02595v1) | December 2015 | 9-layer model w/ 2 layers of 2D-invariant convolution & 7 recurrent layers, w/ 68M parameters |
| 6.30% | 67.94% | 80.27% | [Deep Speech: Scaling up end-to-end speech recognition](http://arxiv.org/abs/1412.5567) | December, 2014 |  CNN + Bi-RNN + CTC (speech to letters) |

TODO

## PER

### TIMIT

(So far, all results trained on TIMIT and tested on the standard test set.)

| PER     | Paper  | Published | Notes   | 
| :------ | :----- | :-------- | :-----: |
| 16.5%   | [Phone recognition with hierarchical convolutional deep maxout networks](http://download.springer.com/static/pdf/26/art%253A10.1186%252Fs13636-015-0068-3.pdf?originUrl=http%3A%2F%2Fasmp.eurasipjournals.springeropen.com%2Farticle%2F10.1186%2Fs13636-015-0068-3&token2=exp=1476195764~acl=%2Fstatic%2Fpdf%2F26%2Fart%25253A10.1186%25252Fs13636-015-0068-3.pdf*~hmac=d0fc51ae80140cbb6b0db06e210c6c3cd80e02bca85b6ba31fa4e593192e50fd) | September 2015 | Hierarchical maxout CNN + Dropout |
| 16.7%   | [Combining Time- and Frequency-Domain Convolution in Convolutional Neural Network-Based Phone Recognition](http://www.inf.u-szeged.hu/~tothl/pubs/ICASSP2014.pdf) | 2014 | CNN in time and frequency + dropout, 17.6% w/o dropout |
| 17.3%   | [Segmental Recurrent Neural Networks for End-to-end Speech Recognition](https://arxiv.org/abs/1603.00223) | March | RNN-CRF on 24(x3) MFSC |
| 17.6%   | [Attention-Based Models for Speech Recognition](http://arxiv.org/abs/1506.07503) | June 2015 | Bi-RNN + Attention |
| 17.7%   | [Speech Recognition with Deep Recurrent Neural Networks](http://arxiv.org/abs/1303.5778v1) | March 2013 | Bi-LSTM + skip connections w/ CTC |
| 18.5%   | [Kaldi's recipe (Karel's DNN)](https://github.com/kaldi-asr/kaldi/blob/master/egs/timit/s5/RESULTS) | 2014 | DNN-HMM + pretraining, fMLLR |
| 23%     | [Deep Belief Networks for Phone Recognition](http://www.cs.toronto.edu/~asamir/papers/NIPS09.pdf) | 2009 | (first, modern) HMM-DBN |

## LM
TODO

## Noise-robust ASR
TODO

## BigCorp™®-specific dataset
TODO?

## Lexicon
 * WER: word error rate
 * PER: phone error rate
 * LM: language model
 * HMM: hidden markov model
 * GMM: Gaussian mixture model
 * DNN: deep neural network
 * CNN: convolutional neural network
 * DBN: deep belief network (RBM-based DNN)
 * RNN: recurrent neural network
 * LSTM: long short-term memory
 * CTC: connectionist temporal classification
 * MMI: maximum mutual information (MMI),
 * MPE: minimum phone error 
 * sMBR: state-level minimum Bayes risk
 * SAT: speaker adaptive training
 * MLLR: maximum likelihood linear regression
 * LDA: (in this context) linear discriminant analysis
 * MFCC: [Mel frequency cepstral coefficients](http://snippyhollow.github.io/blog/2014/09/25/classical-speech-recognition-features-in-one-picture/)
 * FB/FBANKS/MFSC: [Mel frequency spectral coefficients](http://snippyhollow.github.io/blog/2014/09/25/classical-speech-recognition-features-in-one-picture/) 
 * VGG: very deep convolutional neural networks from Visual Graphics Group, VGG is an architecture of 2 {3x3 convolutions} followed by 1 pooling, repeated
