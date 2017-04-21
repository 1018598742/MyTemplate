# File and Code Templates

## 单例模式 (懒汉式)

> ```
> #if (${PACKAGE_NAME} != "")package ${PACKAGE_NAME};#end
>
> #if (${IMPORT_BLOCK} != "")${IMPORT_BLOCK}
> #end
> #parse("File Header.java")
>
> #if (${VISIBILITY} == "PUBLIC")public #end class ${NAME} #if (${SUPERCLASS} != "")extends ${SUPERCLASS} #end #if (${INTERFACES} != "")implements ${INTERFACES} #end {
>     private volatile static ${NAME} ourInstance;
>     private ${NAME}() {}
>     #if (${VISIBILITY} == "PUBLIC")public #end static ${NAME} getInstance() {
>         	if(ourInstance == null){
>   			synchronized (${NAME}.class) {
>   				if(ourInstance == null){
>   					ourInstance = new ${NAME}();
>   				}
>   			}
>   		}
>         return ourInstance;
>     }
> }
> ```

