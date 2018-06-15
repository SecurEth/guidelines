# Tools for Secure Design

Tools are an extremely useful part of the toolset for Developers and Auditors alike to work with code meant for production environments. Tools can reduce human error and speed up development efforts, as well as increase uniformity and optimize code.

It is important however to realize that tools can also abstract away critical review processes that humans typically do, which may lead to scenarios where mistakes are missed and unknown vulnerabilities are added to your code or abstracted out of the design review and testing processes.

Therefore, tools themselves need to follow concrete rules about their operation if they assist in the design or verification process of production code. They should always err on the side of caution, only proceeding with removing human interaction if there is a complete guarantee that it does not introduce new errors, or conceal existing ones.

You should follow the Guidelines for any tool development, add documentation about the [Qualification Status](qualifying-tools.md) of your tool, and finally create a template for a [Tool Report](tool-reports.md)

