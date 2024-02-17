# GAN Training on Valohai

This project shows how to make a basic GAN (Generative Adversarial Network) training script work on Valohai. The original script comes from [Erik Linder-Norén's PyTorch-GAN collection](https://github.com/eriklindernoren/PyTorch-GAN/blob/master/implementations/began/began.py), specifically the BEGAN model.

## What's This For?

The main purpose here is to help you understand what changes you need to make to a normal GAN training script to get it running on Valohai. Valohai is a platform that makes it easier to run, track, and manage your machine learning experiments.

## Changes Made

Here's what we changed in the original script to make it work with Valohai:

1. **valohai.yaml**: We added a file called `valohai.yaml`. This file tells Valohai how to run the script, including the environment, commands and parameters.

2. **Logging**: We changed the script so it sends updates to Valohai while it's running. This is done using a special print statement that outputs JSON.

3. **Saving Files**: The script saves pictures and models to a special folder called `/valohai/outputs`. This is how Valohai keeps track of the files your script creates.

## How to Run It

### Configure the repository:

To run your code on Valohai using the terminal, follow these steps:

1. Install Valohai on your machine by running the following command:
```bash
pip install valohai-cli valohai-utils
```

2. Log in to Valohai from the terminal using the command:
```bash
vh login
```

3. Create a project for your Valohai workflow. 

Start by creating a directory for your project:
```bash
mkdir valohai-gan-example
cd valohai-gan-example
```

4. Clone the repository to your local machine:
```bash
git clone https://github.com/valohai/gan-example.git .
```

5. Then, create the Valohai project and link it:
```bash
vh project create --name gan-test --link 
```



Congratulations! You have successfully cloned the repository, and you can now modify the code and run it using Valohai.

### Running Executions:

To run individual steps, execute the following command:
```bash
vh execution run <step-name> --adhoc
```

For example, to run the preprocess-dataset step, use the command:
```bash
vh execution run gan --adhoc
```

## Conclusion

This project makes it easy to run a GAN training script on Valohai. It's a nice way to use Valohai's tools for your machine learning projects without having to worry too much about the setup.

If you're looking for more information on how to get started with Valohai, check out our [documentation](https://docs.valohai.com/).
