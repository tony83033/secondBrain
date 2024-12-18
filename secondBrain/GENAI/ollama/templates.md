
go templates
// original llama2 template
[INST]

	<<SYS>>
	{{system_prompt}}
		<</SYS>>
	{User_message}
</INST]

// same template with ollama go template formate

[INST]

	<<SYS>>
	{{.System}}
		<</SYS>>
	{{.Prompt}}
</INST]

// . -> variable 

=======================================================

Orca_mini template



