<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "0f7a188d6cb4c18fc83e44fede4cadb1",
  "translation_date": "2025-05-17T12:57:30+00:00",
  "source_file": "03-GettingStarted/samples/csharp/README.md",
  "language_code": "ar"
}
-->
# خدمة الآلة الحاسبة الأساسية MCP

تقدم هذه الخدمة عمليات الآلة الحاسبة الأساسية من خلال بروتوكول نموذج السياق (MCP). تم تصميمها كمثال بسيط للمبتدئين الذين يتعلمون عن تنفيذات MCP.

لمزيد من المعلومات، راجع [C# SDK](https://github.com/modelcontextprotocol/csharp-sdk)

## الميزات

تقدم خدمة الآلة الحاسبة هذه القدرات التالية:

1. **عمليات الحساب الأساسية**:
   - جمع رقمين
   - طرح رقم من آخر
   - ضرب رقمين
   - قسمة رقم على آخر (مع فحص القسمة على الصفر)

## استخدام `stdio` النوع

## الإعداد

1. **تكوين خوادم MCP**:
   - افتح مساحة العمل الخاصة بك في VS Code.
   - قم بإنشاء ملف `.vscode/mcp.json` في مجلد مساحة العمل الخاصة بك لتكوين خوادم MCP. مثال على التكوين:
     ```json
     {
       "servers": {
         "MyCalculator": {
           "type": "stdio",
           "command": "dotnet",
           "args": [
                "run",
                "--project",
                "D:\\source\\03-GettingStarted\\samples\\csharp\\src\\calculator.csproj"
            ],
           "env": {}
         }
       }
     }
     ```
   - استبدل المسار بالمسار إلى مشروعك. يجب أن يكون المسار مطلقًا وليس نسبيًا لمجلد مساحة العمل. (مثال: D:\\gh\\mcp-for-beginners\\03-GettingStarted\\samples\\csharp\\src\\calculator.csproj)

## استخدام الخدمة

تقدم الخدمة نقاط النهاية API التالية من خلال بروتوكول MCP:

- `add(a, b)`: Add two numbers together
- `subtract(a, b)`: Subtract the second number from the first
- `multiply(a, b)`: Multiply two numbers
- `divide(a, b)`: Divide the first number by the second (with zero check)
- isPrime(n): Check if a number is prime

## Test with Github Copilot Chat in VS Code

1. Try making a request to the service using the MCP protocol. For example, you can ask:
   - "Add 5 and 3"
   - "Subtract 10 from 4"
   - "Multiply 6 and 7"
   - "Divide 8 by 2"
   - "Does 37854 prime?"
   - "What are the 3 prime numbers before after 4242?"
2. To make sure it's using the tools add #MyCalculator to the prompt. For example:
   - "Add 5 and 3 #MyCalculator"
   - "Subtract 10 from 4 #MyCalculator


## Containerized Version

The previous soultion is great when you have the .NET SDK installed, and all the dependencies are in place. However, if you would like to share the solution or run it in a different environment, you can use the containerized version.

1. Start Docker and make sure it's running.
1. From a terminal, navigate in the folder `03-GettingStarted\samples\csharp\src` 
1. To build the Docker image for the calculator service, execute the following command (replace `<YOUR-DOCKER-USERNAME>` مع اسم المستخدم الخاص بك في Docker Hub:
   ```bash
   docker build -t <YOUR-DOCKER-USERNAME>/mcp-calculator .
   ``` 
1. بعد بناء الصورة، لنقم برفعها إلى Docker Hub. نفذ الأمر التالي:
   ```bash
    docker push <YOUR-DOCKER-USERNAME>/mcp-calculator
  ```

## استخدام النسخة المعبأة في Docker

1. في ملف `.vscode/mcp.json`، استبدل تكوين الخادم بالتالي:
   ```json
    "mcp-calc": {
      "command": "docker",
      "args": [
        "run",
        "--rm",
        "-i",
        "<YOUR-DOCKER-USERNAME>/mcp-calc"
      ],
      "envFile": "",
      "env": {}
    }
   ```
   بالنظر إلى التكوين، يمكنك أن ترى أن الأمر هو `docker` and the args are `run --rm -i <YOUR-DOCKER-USERNAME>/mcp-calc`. The `--rm` flag ensures that the container is removed after it stops, and the `-i` flag allows you to interact with the container's standard input. The last argument is the name of the image we just built and pushed to Docker Hub.

## Test the Dockerized Version

Start the MCP Server by clicking the little Start button above `"mcp-calc": {`، وكما هو الحال من قبل، يمكنك أن تطلب من خدمة الآلة الحاسبة القيام ببعض العمليات الحسابية لك.

**إخلاء مسؤولية**: 
تمت ترجمة هذه الوثيقة باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار الوثيقة الأصلية بلغتها الأصلية المصدر الموثوق. بالنسبة للمعلومات الهامة، يوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسيرات خاطئة تنشأ عن استخدام هذه الترجمة.