---
title: 商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數和參數值
description: 在商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數和參數值。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1500713a02f85384be5a9cd9a7338b58d3c365f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555449"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數和參數值

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-05_

如果您熟悉在所有 Windows 版本中找到的命令視窗 (，或您熟悉 MS-DOS) ，當您瞭解如何使用 Windows PowerShell 時，您就會有一點的開端。 在命令視窗中輸入命令，然後按 ENTER 鍵。 在回應中，電腦會執行命令或可執行檔。 例如，若要傳回目前目錄中的所有檔案和資料夾的相關資訊，請在命令提示字元中輸入這個命令，然後按 ENTER：

```console
dir
```

接著，您會收到目前目錄中所有檔案和資料夾的相關資訊：

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

當您只輸入命令的名稱或可執行檔時，這是結果的一個範例。 不過，許多從命令視窗中執行的命令也會接受 *引數*。 引數是傳遞給命令的額外資訊片斷，可修改命令的行為。 例如，如果您只想要查看目前目錄中的檔案和資料夾名稱，也就是沒有其他資訊，例如檔案或資料夾的大小，或資料夾或資料夾的建立日期和時間。 在此情況下，您會在執行 dir 命令時附加 **/b** 引數：

```console
dir /b
```

當您包含 **/b** 引數時， **dir** 命令只會傳回目前目錄中的資料夾和檔案的名稱：

```console
Deploy
Intel
PerfLogs
Program Files
Program Files (x86)
Users
Windows
pldok.log
RHDSetup.exe
setup.doc
```

在上述命令中， **/b** 引數是將傳回的資料限制為檔案和資料夾名稱的唯一必要資訊。 使用命令列命令時，通常會發生這種情況：只有引數的實際存在，才能變更命令的行為。  (也就是說，您可以包含 **/b** 引數以隱藏其他資訊，或排除 **/b** 引數以顯示額外的資訊。 ) 其他情況下，您必須指定 *引數值*。 引數值是傳遞給引數本身的其他資訊。 例如， **/o** 引數可讓您指定您想要 dir 命令如何排序傳回的資料。 在其他選項中，您可以使用引數值 **e** ，依副檔名或引數值 **s** 排序，依檔案大小排序。 例如，此命令會依照副檔名排序傳回的資料。 請注意 **/o**引數後緊接著包含引數值**e**的方式：

```console
dir /oe
```

使用我們的範例資料夾，傳回的資料會如下列所示，並依照副檔名排序：

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

或者，為了協助您準確指出我們所談論的專案：

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

雖然 Windows PowerShell 使用不同的術語，但使用 Windows PowerShell 的基本方法與使用命令視窗相同：您可以輸入命令，視需要包含引數和引數值，然後按 ENTER 執行這些命令。 不過請注意，Windows PowerShell 會使用不同于命令介面所用的術語。 在 Windows PowerShell 中，您執行的命令稱為 *Cmdlet*。 接著，傳遞至 Cmdlet 的參數稱為 *參數*，傳遞給參數的值稱為 *參數值*。

前面的定義已有些簡化。 Cmdlet 基本上是迷你應用程式，只能在 Windows PowerShell 環境內執行。 不過，您也可以在 Windows PowerShell 中執行其他命令和應用程式，包括可以從命令視窗執行的大部分命令和應用程式。 例如，如果您想要在 Windows PowerShell 內啟動 [記事本]，您只需要輸入下列專案，然後按 ENTER：

```console
notepad.exe
```

不過，若要管理商務用 Skype Online，大部分系統管理員會依賴 Windows PowerShell Cmdlet 來執行系統管理工作。 在時，有些其他類型的命令或應用程式可以用來管理商務用 Skype Online。 有時候，您可以使用商務用 Skype Online Cmdlet，而不需要任何其他引數 ( （如前文所述），引數稱為 Windows PowerShell) 中的參數。 例如，下列命令會呼叫沒有任何其他參數的 [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) Cmdlet。 命令會傳回所有商務用 Skype Online 使用者的相關資訊：

```powershell
Get-CsOnlineUser
```

不過，大部分商務用 Skype Online Cmdlet 也會接受 (和參數值) 的參數。 請考慮下列命令：

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

這個命令包含三個部分：

  - Cmdlet **Get-CsOnlineUser**。

  - Identity 參數。 請注意，在 Windows PowerShell 中，參數永遠會以破折號 ( ) 開頭。 這表示，針對這個相同的 Cmdlet，UnassignedUser 參數會使用下列語法來表示：
    
    ```powershell
    -UnassignedUser
    ```
    
    這有助於知道，不只是因為參數必須以短劃線開頭，但由於這與命令視窗不同，其引數是使用正斜線 (/) 開頭的：
    
    ```console
    /b
    ```

  - 參數值 **kenmyer@litwareinc.com**。

該命令會傳回特定使用者的資訊： identity 為 kenmyer@litwareinc.com 的使用者。

<div>

## <a name="see-also"></a>另請參閱


[Windows PowerShell 和商務用 Skype Online 簡介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

