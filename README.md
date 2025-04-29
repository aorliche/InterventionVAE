# InterventionVAE
Variational autoencoder for counterfactual intervention on phenotypes. Applied to intervention on non-modifiable/genetic factors, modifiable factors, and physiological measurements to measure increase or decrease in FC-mediated Alzheimer's disease (AD) risk.

This is originally based on the demo-vae package, but applied to the study of AD.

# Installation

Run 

```
pip install demovae
```

to install demovae along with basic dependencies (numpy, scikit-learn, and torch).

Check the file <a href='https://github.com/aorliche/InterventionVAE/blob/main/test/Pip3TestSample.ipynb'>Pip3TestSample.ipynb</a> for a basic idea of how to run the code.

Check <a href='https://github.com/aorliche/demo-vae/blob/main/pip/src/demovae/sklearn.py'>this file</a> in the pip subdirectory to see all of the configuration parameters you can set, e.g.:

```
    @staticmethod
    def get_default_params():
        return dict(latent_dim=60,      # Latent dimension
                use_cuda=True,          # GPU acceleration
                nepochs=3000,           # Training epochs
                pperiod=100,            # Epochs between printing updates 
                bsize=1000,             # Batch size
                loss_C_mult=1,          # Covariance loss (KL div)
                loss_mu_mult=1,         # Mean loss (KL div)
                loss_rec_mult=100,      # Reconstruction loss
                loss_decor_mult=10,     # Latent-demographic decorrelation loss
                loss_pred_mult=0.001,   # Classifier/regressor guidance loss
                alpha=100,              # Regularization for continuous guidance models
                LR_C=100,               # Regularization for categorical guidance models
                lr=1e-4,                # Learning rate
                weight_decay=0,         # L2 regularization for VAE model
                )
```

# API

The DemoVAE class uses the scikit-learn API. You have access to the following methods:

```
DemoVAE
fit
transform
fit_transform
get_latents
save
load
```

Check the `pip/src/demovae` directory for how to use them.

# AD Study Overview

The overview of demovae applied to interventions on modifiable risk factors for AD is shown below:

<img src='https://github.com/aorliche/InterventionVAE/blob/a86418b974afc6566fd34ceff50eddfd173a5341/image/GraphicalAbstract.png' width='800'>

Please <a href='mailto:anton.orlichenko@yale.edu'>contact me</a> for any questions.

