I picked Python for this exercise as I've used the language a little bit and I'm interested in learning more. Learning how the ci/cd-stack is usually constructed seemed like a useful thing to learn. 

Linting in Python can be done with pylint, which checks for errors and code smells and enforces a certain coding styling. Pylint is invoked by running the command ```pylint [options] module_or_package```, for example: ```pylint main.py```. [1]

For testing there is pytest, which I've already used myself in a course on software testing. Pytest requires Python 3.8+ or PyPy3 to be installed. The test files are usually named with the "test_"-prefix, e.g. "test_main.py" and the tests can be run (in the simplest case) just by invoking the ```pytest``` command. [2]

There is no need for a build step for Python, as it's an interpreted language; so no compilation is necessary. This makes the ci/cd-setup simpler as opposed to compiled languages, such as Java, which is also in line with Pythons simplistic philosophy.

CircleCI is one alternative for setting up a ci/cd-pipeline. [3] For setting up CircleCI you need to create a ```.circleci/config.yml``` file in the root of the project. The CircleCI website contains a tutorial for setting up a Python ci/cd pipeline in Heroku. [4]

Deciding whether to use a self-hosted or cloud-based environment depends on the complexity of the project, number of repositories and how much customization is required for the ci/cd-pipeline. Self-hosted ci/cd solutions (using e.g. Jenkins) can be a better fit for large codebases that require highly customised setups. They can also save money as costs are only based on the hardware. I would prefer self-hosted setups only for very complex projects as cloud-based setups are much easier and faster to get up running. [5]

Since the application in this case has just 6 people working on it, it probably isn't that large of a project, so I think a cloud-based environment would be more suitable. 


References:  
[1] https://docs.pylint.org/run.html#invoking-pylint 
[2] https://docs.pytest.org/en/stable/getting-started.html#get-started  
[3] https://circleci.com/product/  
[4] https://circleci.com/docs/language-python/  
[5] https://fullstackopen.com/en/part11/introduction_to_ci_cd#packaging-and-deployment-as-a-part-of-ci