# import 命令
使用export命令定义了模块的对外接口以后，其他 JS 文件就可以通过import命令加载这个模块。

    // main.js
    import {firstName, lastName, year} from './profile';
    
    function setName(element) {
      element.textContent = firstName + ' ' + lastName;
    }
上面代码的import命令，用于加载profile.js文件，并从中输入变量。import命令接受一对大括号，里面指定要从其他模块导入的变量名。大括号里面的变量名，必须与被导入模块（profile.js）对外接口的名称相同。


如果想为输入的变量重新取一个名字，import命令要使用as关键字，将输入的变量重命名。

    import { lastName as surname } from './profile';
import后面的from指定模块文件的位置，可以是相对路径，也可以是绝对路径，.js后缀可以省略。如果只是模块名，不带有路径，那么必须有配置文件，告诉 JavaScript 引擎该模块的位置。

    import {myMethod} from 'util';
上面代码中，util是模块文件名，由于不带有路径，必须通过配置，告诉引擎怎么取到这个模块。

**注意，import命令具有提升效果，会提升到整个模块的头部，首先执行。**