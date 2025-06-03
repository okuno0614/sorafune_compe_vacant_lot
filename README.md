# vacant_lot

## 20250603：提出結果は0.39
bboxは幅・高さが両方20px超のものだけ残し、それ以下の小さいものを削除
cfg.SOLVER.IMS_PER_BATCH = 8
cfg.SOLVER.BASE_LR = 0.00025
cfg.SOLVER.MAX_ITER = 3000
cfg.MODEL.ROI_HEADS.BATCH_SIZE_PER_IMAGE = 128
cfg.MODEL.ANCHOR_GENERATOR.SIZES = [[16],[32], [64], [128], [256]] 
cfg.MODEL.ANCHOR_GENERATOR.ASPECT_RATIOS = [[0.5, 1.0, 2.0]] 
cfg.TEST.EVAL_PERIOD = 300
cfg.SOLVER.WARMUP_ITERS = 300
cfg.SOLVER.WARMUP_METHOD = "linear"
cfg.SOLVER.WARMUP_FACTOR = 0.1
cfg.SOLVER.STEPS = (2000, 2600)
cfg.SOLVER.GAMMA = 0.1 
cfg.MODEL.ROI_HEADS.SCORE_THRESH_TEST = 0.3 #閾値
cfg.MODEL.ROI_HEADS.NMS_THRESH_TEST = 0.3 #NMS IoU

- segmentation_v1
  - 学習データを7:3にランダム分割して、7割で学習した結果
  - モデルはDeep Lab v3を利用
  - サンプルのbboxと合わせて提出した際のスコアは0.0055596
  - ※学習、推論時の画像リサイズを戻し忘れているため、スコアは低い
  - ※サンプルbbox,segmentationでの提出スコアは0.0055432
