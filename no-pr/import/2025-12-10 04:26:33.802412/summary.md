Traceback (most recent call last):
  File "/usr/local/lib/python3.11/site-packages/botocore/parsers.py", line 503, in _parse_xml_string_to_dom
    parser.feed(xml_string)
xml.etree.ElementTree.ParseError: syntax error: line 1, column 0

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/app/iambic/plugins/v0_1_0/github/github.py", line 558, in wrapped_workflow_func
    template_changes = workflow_func(repo_url, default_branch)
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/plugins/v0_1_0/github/github.py", line 723, in _handle_import
    raise e
  File "/app/iambic/plugins/v0_1_0/github/github.py", line 713, in _handle_import
    asyncio.run(config.run_import(exe_message, repo_dir))
  File "/Python-3.11.1/Lib/asyncio/runners.py", line 190, in run
    return runner.run(main)
           ^^^^^^^^^^^^^^^^
  File "/Python-3.11.1/Lib/asyncio/runners.py", line 118, in run
    return self._loop.run_until_complete(task)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Python-3.11.1/Lib/asyncio/base_events.py", line 653, in run_until_complete
    return future.result()
           ^^^^^^^^^^^^^^^
  File "/app/iambic/config/dynamic_config.py", line 228, in run_import
    await asyncio.gather(*tasks)
  File "/app/iambic/plugins/v0_1_0/aws/handlers.py", line 307, in import_aws_resources
    await asyncio.gather(*tasks)
  File "/app/iambic/plugins/v0_1_0/aws/handlers.py", line 218, in import_service_resources
    await asyncio.gather(*tasks)
  File "/app/iambic/plugins/v0_1_0/aws/iam/role/template_generation.py", line 532, in collect_aws_roles
    await set_role_resource_inline_policies_semaphore.process(messages)
  File "/app/iambic/core/utils.py", line 205, in process
    return await asyncio.gather(
           ^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/core/utils.py", line 200, in handle_message
    return await self.callback_function(**kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/plugins/v0_1_0/aws/iam/role/template_generation.py", line 187, in set_role_resource_inline_policies
    role_inline_policies = await get_role_inline_policies(role_name, iam_client)
                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/plugins/v0_1_0/aws/iam/role/utils.py", line 71, in get_role_inline_policies
    policy_names = await get_role_inline_policy_names(role_name, iam_client)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/plugins/v0_1_0/aws/iam/role/utils.py", line 19, in get_role_inline_policy_names
    return await paginated_search(
           ^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/plugins/v0_1_0/aws/utils.py", line 95, in paginated_search
    response = await boto_crud_call(search_fnc, **search_kwargs)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/plugins/v0_1_0/aws/utils.py", line 46, in boto_crud_call
    return await aio_wrapper(boto_fnc, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/app/iambic/core/utils.py", line 162, in aio_wrapper
    return await sync_to_async(fnc, thread_sensitive=thread_sensitive)(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/asgiref/sync.py", line 448, in __call__
    ret = await asyncio.wait_for(future, timeout=None)
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Python-3.11.1/Lib/asyncio/tasks.py", line 442, in wait_for
    return await fut
           ^^^^^^^^^
  File "/Python-3.11.1/Lib/concurrent/futures/thread.py", line 58, in run
    result = self.fn(*self.args, **self.kwargs)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/asgiref/sync.py", line 490, in thread_handler
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/client.py", line 530, in _api_call
    return self._make_api_call(operation_name, kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/client.py", line 943, in _make_api_call
    http, parsed_response = self._make_request(
                            ^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/client.py", line 966, in _make_request
    return self._endpoint.make_request(operation_model, request_dict)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/endpoint.py", line 119, in make_request
    return self._send_request(request_dict, operation_model)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/endpoint.py", line 199, in _send_request
    success_response, exception = self._get_response(
                                  ^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/endpoint.py", line 241, in _get_response
    success_response, exception = self._do_get_response(
                                  ^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/endpoint.py", line 308, in _do_get_response
    parsed_response = parser.parse(
                      ^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/parsers.py", line 250, in parse
    parsed = self._do_error_parse(response, shape)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/parsers.py", line 557, in _do_error_parse
    root = self._parse_xml_string_to_dom(xml_contents)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/local/lib/python3.11/site-packages/botocore/parsers.py", line 506, in _parse_xml_string_to_dom
    raise ResponseParserError(
botocore.parsers.ResponseParserError: Unable to parse response (syntax error: line 1, column 0), invalid XML received. Further retries may succeed:
b'Internal Failure'
