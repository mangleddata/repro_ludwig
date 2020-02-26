# repro_ludwig

- Unzip data.zip to get train.csv/valid.csv/test.csv Files
- Use run.sh to run a trainer for 2 epochs [*horovodrun -np 2 --stall-check-shutdown-time-seconds 120 ludwig train --data_train_csv  train.csv --data_validation_csv  valid.csv --data_test_csv test.csv -mdf repro.yaml -uh --model_name repro -sspi *]
- Now train again using the saved model using rerun.sh [*horovodrun -np 2 --stall-check-shutdown-time-seconds 120 ludwig train --data_train_csv  train.csv --data_validation_csv  valid.csv --data_test_csv test.csv -mdf repro.yaml -uh  --model_name repro -sspi -mlp ./results/experiment_repro/model *]
  - Alternatively, you could simply try rerunning using the results.zip below which contains a trained model in experiment_repro
  - https://s3.amazonaws.com/mangleddata/results.zip
