.. Copyright 2010-2018 Amazon.com, Inc. or its affiliates. All Rights Reserved.

   This work is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 4.0
   International License (the "License"). You may not use this file except in compliance with the
   License. A copy of the License is located at http://creativecommons.org/licenses/by-nc-sa/4.0/.

   This file is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
   either express or implied. See the License for the specific language governing permissions and
   limitations under the License.

#################################################
Invoking, Listing, and Deleting Lambda Functions
#################################################

.. meta::
    :description: How to invoke, list, and delete a Lambda function by using the AWS SDK for Java 2.x.
    :keywords: Amazon Lambda, AWS SDK for Java 2.x, Lambda code examples,
               deleteFunction, invoke, listFunctions


This section provides examples of programming with the Lambda service client by using the AWS SDK for Java 2.0.

.. contents::
    :local:
    :depth: 1

.. _invoke-function:
Invoke a Lambda function
========================

You can invoke a Lambda function by creating a :aws-java-class:`LambdaClient <services/lambda/LambdaClient>`
object and invoking its :methodname:`invoke` method. Create an :aws-java-class:`InvokeRequest <services/lambda/model/InvokeRequest>`
object to specify additional information such as the function name and the payload to pass to the Lambda function. Function names
appear as *arn:aws:lambda:us-west-2:555556330391:function:HelloFunction*. You can retrieve the value by looking at the function in the AWS Console.

To pass payload data to a function, create a :aws-java-class:`SdkBytes <core/SdkBytes>`
object that contains information. For example, in the following code example, notice the JSON data passed to the Lambda function.

**Imports**

.. literalinclude:: lambda.java2.invoke.import.txt
   :language: java

**Code**

The following code example demonstrates how to invoke a Lambda function.

.. literalinclude:: lambda.java2.invoke.main.txt
   :dedent: 4
   :language: java

See the complete example on `Github
<https://github.com/awsdocs/aws-doc-sdk-examples/blob/master/javav2/example_code/lambda/src/main/java/com/example/lambda/LambdaInvoke.java/>`_.


.. _list-function:

List Lambda functions
=========================

Build a :aws-java-class:`LambdaClient <services/lambda/LambdaClient>`
object and invoke its :methodname:`listFunctions` method.
This method returns a :aws-java-class:`ListFunctionsResponse <services/lambda/model/ListFunctionsResponse>` object.
You can invoke this object's :methodname:`functions` method to return a list of :aws-java-class:`FunctionConfiguration <services/lambda/model/FunctionConfiguration>` objects.
You can iterate through the list to retrieve information about the functions. For example, the following Java code example shows how to get each function name.


**Imports**

.. literalinclude:: lambda.java2.list.import.txt
   :language: java

**Code**

The following Java code example demonstrates how to retrieve a list of function names.

.. literalinclude:: lambda.java2.list.main.txt
   :dedent: 4
   :language: java

See the complete example on `Github
<https://github.com/awsdocs/aws-doc-sdk-examples/blob/master/javav2/example_code/lambda/src/main/java/com/example/lambda/ListLambdaFunctions.java/>`_.


.. _delete-function:

Delete a Lambda function
========================

Build a :aws-java-class:`LambdaClient <services/lambda/LambdaClient>`
object and invoke its :methodname:`deleteFunction` method.
Create a :aws-java-class:`DeleteFunctionRequest <services/lambda/model/DeleteFunctionRequest>`
object and pass it to the :methodname:`deleteFunction` method. This object contains information such as the name of the function to delete.
Function names appear as *arn:aws:lambda:us-west-2:555556330391:function:HelloFunction*. You can retrieve the value by looking at the function in the AWS Console.

**Imports**

.. literalinclude:: lambda.java2.delete.import.txt
   :language: java

**Code**

The following Java code demonstrates how to delete a Lambda function.

.. literalinclude:: lambda.java2.delete.main.txt
   :dedent: 4
   :language: java

See the complete example on `Github
<https://github.com/awsdocs/aws-doc-sdk-examples/blob/master/javav2/example_code/lambda/src/main/java/com/example/lambda/DeleteFunction.java/>`_.


