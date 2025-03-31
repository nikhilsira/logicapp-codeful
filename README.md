# test-workspace

* After building, add the following into the `function.json` file in the following dirs: `bin\net8.0\Debug\[TimerTrigger1, Function1]`:
```  
  "inputSchema": { },
  "outputSchema": { }
```

Otherwise the following exception occurs:

```
[2024-09-17T20:20:00.537Z] Workflow processing failed. Error: 'For the 'invokeFunction' action, the associated function metadata file named 'Q:\src\logicapps-code-poc\TestFunc\bin\Debug\net6.0\SayHello\function.json' has an 'InputSchema' property value that's null or empty. Make sure that the 'InputSchema' property contains the correct input schema for the associated function.'
[2024-09-17T20:20:00.539Z] Workflow Error: operationName='WorkflowFunctionDefinitionProvider.GetFunctionMetadataAsync', message='Workflow processing failed. Error: 'For the 'invokeFunction' action, the associated function metadata file named 'Q:\src\logicapps-code-poc\TestFunc\bin\Debug\net6.0\SayHello\function.json' has an 'InputSchema' property value that's null or empty. Make sure that the 'InputSchema' property contains the correct input schema for the associated function.'', exception='Microsoft.Azure.Workflows.Common.ErrorResponses.ErrorResponseMessageException: For the 'invokeFunction' action, the associated function metadata file named 'Q:\src\logicapps-code-poc\TestFunc\bin\Debug\net6.0\SayHello\function.json' has an 'InputSchema' property value that's null or empty. Make sure that the 'InputSchema' property contains the correct input schema for the associated function.
[2024-09-17T20:20:00.541Z]    at Microsoft.Azure.Workflows.Data.Providers.EdgeFunctionFileDataProvider.GetFunctionFileParsedInput(String fileName, String rootDirectory)
[2024-09-17T20:20:00.542Z]    at Microsoft.Azure.Workflows.Data.Providers.EdgeFunctionFileDataProvider.<>c__DisplayClass6_0.<<GetFunctionFileData>b__0>d.MoveNext()
[2024-09-17T20:20:00.543Z] --- End of stack trace from previous location ---
[2024-09-17T20:20:00.544Z]    at Microsoft.WindowsAzure.ResourceStack.Common.Extensions.ConcurrencyExtensions.ExecuteOperationsConcurrently[TElement](IEnumerable`1 source, Func`3 operation, Int32 concurrencyLimit, CancellationToken cancellationToken)
[2024-09-17T20:20:00.546Z]    at Microsoft.Azure.Workflows.Data.Providers.EdgeFunctionFileDataProvider.GetFunctionFileData(String rootDirectory)
[2024-09-17T20:20:00.547Z]    at Microsoft.Azure.Workflows.WebJobs.Extensions.Initialization.WorkflowFunctionDefinitionProvider.ProcessWorkflowFiles()
[2024-09-17T20:20:00.548Z]    at Microsoft.Azure.Workflows.WebJobs.Extensions.Initialization.WorkflowFunctionDefinitionProvider.GetFunctionMetadataAsync()', extensionVersion='1.81.39.0', siteName='UNDEFINED_SITE_NAME', slotName='', activityId='00000000-0000-0000-0000-000000000000'.
