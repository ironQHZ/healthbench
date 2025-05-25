# healthbench-OpenAI

This repository is based on https://github.com/openai/simple-evals, with compatibility fixes for running qwen and deepseek

Original project is licensed under the MIT License.

## Setup (copy)
Due to the optional dependencies, we're not providing a unified setup mechanism. Instead, we're providing instructions for each eval and sampler.

For HumanEval (python programming)

git clone https://github.com/openai/human-eval
pip install -e human-eval
For the OpenAI API:

pip install openai
For the Anthropic API:

pip install anthropic

## Running the evals (copy)
python -m simple-evals.simple_evals --list-models
This will list all the models that you can evaluate.

To run the evaluations, you can use the following command:

python -m simple-evals.simple_evals --model <model_name> --examples <num_examples>
This will launch evaluations through the OpenAI API.
*To run all 5000 examples, simply ignore the --examples flag.

## notes
- 1. The original code use gpt-4.1 as the grader. I changed it to gpt-4.1-mini during testing. You can try other models. Just search for "grading_sampler".
- 2. The original repo also runs several other benchmarks like MMLU/GPQA, although they are not mentioned in the paper. If you want to run them, go to the end of simple_evals.py and uncomment the benchmarks you would like to try.
- 3. Result files will be generated in ./tmp
- 4. check ./data for dataset info