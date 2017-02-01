# PoorManScriptingLanguageWeb

A STATELESS workflow engine ;-)

Pre-alpha - use at your own risk...

## Sample

Cmd:
```
cat forkjointest.pmsl	
```
Result:
```
workflow forkjointest
	node start
		transition to left
		transition to right
		
		enter
			left = ""
			right = ""
		end
	end
	
	state left
		transition to done
		
		enter
			left = "enter"
		end
		
		leave
			left = "leave " + getParam("x")
		end
	end
	
	state right
		transition to done
	
		enter
			right = "enter"
		end
		
		leave
			right = "leave " + getParam("x")
		end
	end
	
	join done
		enter
		  done = "enter " + getParam("x")
		end
	end
end
```
