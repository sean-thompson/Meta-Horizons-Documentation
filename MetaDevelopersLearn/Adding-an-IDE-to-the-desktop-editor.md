# Adding an IDE to the desktop editor

[source](https://developers.meta.com/horizon-worlds/learn/documentation/typescript/getting-started/adding-an-ide-to-desktop-editor)

You will need an IDE to write your own scripts for Meta Horizon Worlds. By default, the desktop editor uses [Visual Studio Code](https://code.visualstudio.com/download) , but if you want to use a different editor, you can configure it to use another IDE instead.

To configure the desktop editor, you need to make sure that you use version 4.7.4 of TypeScript. While you can use other versions of TypeScript, you may encounter issues when you use them with Meta Horizon Worlds APIs. If you don’t have TypeScript installed yet or you’re uncertain what version you’ve got, see [Managing Typescript](/horizon-worlds/learn/documentation/typescript/getting-started/managing-typescript/) .

Whichever IDE you choose to use, you will need to configure the desktop editor to use it. Steps to do so can be found below:

*   [Using VS Code with the desktop editor](#configure-the-desktop-editor-to-use-vs-code)

*   [Using another third-party IDE with the desktop editor](#using-another-third-party-ide-with-the-desktop-editor)

## Using VS Code with the desktop editor

This section shows you how to set up Visual Studio Code (VS Code) for editing TypeScript scripts with the desktop editor. **Configure the desktop editor to use VS Code** *   If it’s not already installed on your computer, install the latest version of VS Code from the [VS Code website](https://code.visualstudio.com/) .
    

*   Ensure that you have version 4.7.4 of TypeScript installed. For more information on doing this, see [Managing Typescript](/horizon-worlds/learn/documentation/typescript/getting-started/managing-typescript/) .
    

*   Note the file path to where VS Code is installed on your computer. You’ll need this in the following steps.
    

*   Open the Meta Horizon Worlds desktop editor and then open the **Scripts** panel.
    
    ![The Scripts Panel](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/482960441_673266571877964_3333170914423766306_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=-3e0NyL_-pMQ7kNvwHCMI39&_nc_oc=AdlMbnS9Ijp1GhcRsmtTMDrvf2TW9MlCJHxR0IHIm5Ad8gDW9uC-V1gQq3GgJOaO3IY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=2EGeBJurH7cN9jQe1GADZQ&oh=00_AfQ-1BrEsoQickjHI2LrP7ASHXmL8hOJM7NtB0AvRRkxRg&oe=689BB954)
    

*   Click the gear-shaped icon to open **Settings**.
    
    ![The Scripts panel with mouse over Settings icon](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/484420212_673266585211296_193404919351644516_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=vWTHGeGpY4EQ7kNvwFL3Ssf&_nc_oc=AdkxrxXDgYag2fPEdKpUW1IcDWNSNCJ7qTnAuwYvX8ewGbiE38xw_Z-zx2BFi7QlEVE&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=2EGeBJurH7cN9jQe1GADZQ&oh=00_AfTl21LbPYB_XPSCcTxb8SljauhBoQE708mziMQIce8zJQ&oe=689BA3C3)
    

*   Next to **External Editor**, click **Select**.
    
    ![Script Settings dialog box](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/482961279_673266621877959_676465629114660006_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=HOeqklE3xkAQ7kNvwH2uXf-&_nc_oc=AdmSqStIMglVIO8U9ZJMW6FnxoPiFBXewqIQ2m1_j364LqpIZoEgESHvp2ViDSEyUFY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=2EGeBJurH7cN9jQe1GADZQ&oh=00_AfQf6Q7PzDuOtI4xO2HGEeL9WrpbIRf5EjCJDyH48tCWIw&oe=689BABA2)
    

*   Paste the file path from Step 3 into the **File name** field and then click **Open**. You can also navigate to the EXE file for your IDE and then click **Open**.
    

*   Click **Apply** to set VS Code as the external editor.
    

## Using another third-party IDE with the desktop editor

These section shows you how to set up the desktop editor to use an IDE other than VS Code as the default IDE.

*   Ensure that you have version 4.7.4 of TypeScript installed. For more information on doing this, see [Managing Typescript](/horizon-worlds/learn/documentation/typescript/getting-started/managing-typescript/) .
    

*   If it’s not already installed on your computer, install the latest version of your third-party IDE.
    

*   Note the file path to where the EXE file for your IDE is installed on your computer. You’ll need this in the following steps.
    

*   Open the Meta Horizon Worlds desktop editor and then open the **Scripts** panel.
    
    ![The Scripts Panel dropdown](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/482960441_673266571877964_3333170914423766306_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=-3e0NyL_-pMQ7kNvwHCMI39&_nc_oc=AdlMbnS9Ijp1GhcRsmtTMDrvf2TW9MlCJHxR0IHIm5Ad8gDW9uC-V1gQq3GgJOaO3IY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=2EGeBJurH7cN9jQe1GADZQ&oh=00_AfQ-1BrEsoQickjHI2LrP7ASHXmL8hOJM7NtB0AvRRkxRg&oe=689BB954)
    

*   Click the gear-shaped icon to open **Settings**.
    

*   Next to **External Editor**, click **Select**.
    
    ![Script Settings dialog box](https://scontent.flba1-1.fna.fbcdn.net/v/t39.2365-6/482961279_673266621877959_676465629114660006_n.png?_nc_cat=104&ccb=1-7&_nc_sid=e280be&_nc_ohc=HOeqklE3xkAQ7kNvwH2uXf-&_nc_oc=AdmSqStIMglVIO8U9ZJMW6FnxoPiFBXewqIQ2m1_j364LqpIZoEgESHvp2ViDSEyUFY&_nc_zt=14&_nc_ht=scontent.flba1-1.fna&_nc_gid=2EGeBJurH7cN9jQe1GADZQ&oh=00_AfQf6Q7PzDuOtI4xO2HGEeL9WrpbIRf5EjCJDyH48tCWIw&oe=689BABA2)
    

*   Paste the file path from Step 3 into the **File name** field and then click **Open**. You can also navigate to the EXE file for your IDE and then click **Open**.
    

*   Click **Apply** to set VS Code as the external editor.
    

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 