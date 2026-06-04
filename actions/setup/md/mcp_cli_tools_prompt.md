<mcp-clis>
CLI servers are available on `PATH`:
__GH_AW_MCP_CLI_SERVERS_LIST__
Use `<server> --help` for tool names, parameters, and examples before calling any command.
To pass multiple or complex arguments to an MCP CLI command, supply a JSON object on stdin using `.` as the sentinel. The bridge parses stdin as the argument object, preserving all native types (numbers, booleans, arrays) without shell-quoting issues.
```bash
printf '{"item_number":42,"body":"### Title\n\nBody paragraph one.\n\nBody paragraph two."}' \
  | safeoutputs add_comment .
```
If pipes are blocked by bash policy, write JSON to a file and use redirection with `.` (for example: `safeoutputs create_pull_request . < /tmp/payload.json`).
</mcp-clis>
