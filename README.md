# CompoSeqAug

CompoSeqAug is a collection of compositional sequence-to-sequence data augmentation experiments using the OpenNMT framework. This repository contains data, configurations, and model checkpoints for exploring the impact of various augmentation strategies on sequence modeling tasks, such as neural machine translation.

## Project Structure

- `data/`: Source and target text files for training, validation, and testing. Includes both original and augmented datasets.
- `onmt/`: Vocabulary files for different experimental setups.
  - `aug/`: Vocabularies for augmented data experiments.
  - `base/`: Vocabularies for the baseline experiment.
- `models/`: Pre-trained model checkpoints (`.pt` files) for each experiment.
- `pred/`: Model predictions for different experimental setups.
- `train_*.yaml`, `vocab_*.yaml`: Configuration files for training and vocabulary settings, specifying data paths, vocabularies, and model parameters.
- `.gitignore`: Git version control settings.

## Experiments

The following experimental setups are included:
- **base**: Baseline model trained on original data.
- **aug1**, **augp**, **augpr**, **augr**: Models trained with various data augmentation strategies.

Each experiment has corresponding:
- Training/validation data files
- Vocabulary files
- Model checkpoints
- Prediction outputs

## Usage

1. **Training**: Use the provided YAML config files with OpenNMT to train models. Example:
   ```bash
   onmt_train -config train_aug_1.yaml
   ```
2. **Inference**: Use trained models to generate predictions:
   ```bash
   onmt_translate -model models/aug1.pt -src data/src_test.txt -output pred/aug1.txt
   ```
3. **Evaluation**: Compare predictions in `pred/` with reference targets in `data/tgt_test.txt` using standard metrics (e.g., BLEU).

## Requirements

- [OpenNMT-py](https://github.com/OpenNMT/OpenNMT-py)
- Python 3.x
- PyTorch

## License

MIT

## Acknowledgements

- [OpenNMT](https://opennmt.net/)
