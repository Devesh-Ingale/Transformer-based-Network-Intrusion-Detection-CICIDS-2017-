# Transformer-based-Network-Intrusion-Detection-CICIDS-2017-
Built a Transformer-based NIDS on CICIDS-2017 with class-balanced focal loss and a production-ready training/eval stack (AMP, AdamW, warmup-cosine, early-stop on macro-F1).

Dataset: CICIDS-2017 (multiclass attacks).

Model: TabularTransformer(d_model=96, n_heads=4, n_layers=4, ffw=256, dropout=0.2), CLS pooling.

Loss: ClassBalancedFocalLoss(β=0.999, γ=1.5, clip=10) on CE.

Train: AdamW, AMP, warmup→cosine, grad-clip=1.0, early stop on macro-F1.

Eval: classification_report, balanced acc, MCC, κ, confusion matrix.

Repro: stratified 70/15/15 split; StandardScaler on train only; saved best ckpt.
