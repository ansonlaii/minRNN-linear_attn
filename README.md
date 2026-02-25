This is the final project code for the course CS679 (Neural Networks) in University of Waterloo. 

The project is based on the paper [Were RNNs All We Needed?](https://arxiv.org/pdf/2410.01201). The authors of the paper sought out to show that their minRNN models are more efficient than other state of the art models but still achieve competitive accuracies in basic tasks like selective copying. We followed the suggestion of the paper to reevaluate simpler foundational models in light of more complex architectures. In particular, we added linearized attention instead of the traditional softmax attention to minRNN which allows parallel scan, in effect achieving faster runtimes.

Our experiment is based on the selective copying task where our models (minRNN + linearized attention) achieved slightly better accuracies as shown below, with the downside of slightly longer runtimes. To see a comparison of runtimes between our models and minRNN, check out our paper [Enhancing minRNN With Linearized Attention](https://drive.google.com/file/d/1pWOz_LoPbWE0vS3LzlReAEJFFmFzmoB2/view?usp=sharing).

| Model              | Test Accuracy     |
|--------------------|------------------|
| GRU                | 31.5 ± 0.4       |
| LSTM               | 32.5 ± 0.6       |
| minGRU             | 81 ± 0.3         |
| minLSTM            | 80 ± 0.5         |
| minGRU w/ ATN      | 84 ± 0.4         |
| minLSTM w/ ATN     | 83 ± 0.9         |
**Table 1:** Model Accuracies on Selective Copying Task

