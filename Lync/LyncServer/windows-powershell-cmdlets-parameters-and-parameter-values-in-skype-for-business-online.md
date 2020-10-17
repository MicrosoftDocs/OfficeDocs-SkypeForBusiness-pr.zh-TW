---
title: 商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數和參數值
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
ms.openlocfilehash: 50ad45c9deecf364c273ff64e939c4379d169f3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499960"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="b61a5-102">商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數和參數值</span><span class="sxs-lookup"><span data-stu-id="b61a5-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b61a5-103">_**主題上次修改日期：** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="b61a5-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="b61a5-104">如果您熟悉在所有 Windows 版本中找到的命令視窗 (，或您熟悉 MS-DOS) ，當您瞭解如何使用 Windows PowerShell 時，您就會有一點的開端。</span><span class="sxs-lookup"><span data-stu-id="b61a5-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="b61a5-105">在命令視窗中輸入命令，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="b61a5-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="b61a5-106">在回應中，電腦會執行命令或可執行檔。</span><span class="sxs-lookup"><span data-stu-id="b61a5-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="b61a5-107">例如，若要傳回目前目錄中的所有檔案和資料夾的相關資訊，請在命令提示字元中輸入這個命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="b61a5-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="b61a5-108">接著，您會收到目前目錄中所有檔案和資料夾的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b61a5-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="b61a5-109">當您只輸入命令的名稱或可執行檔時，這是結果的一個範例。</span><span class="sxs-lookup"><span data-stu-id="b61a5-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="b61a5-110">不過，許多從命令視窗中執行的命令也會接受 *引數*。</span><span class="sxs-lookup"><span data-stu-id="b61a5-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="b61a5-111">引數是傳遞給命令的額外資訊片斷，可修改命令的行為。</span><span class="sxs-lookup"><span data-stu-id="b61a5-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="b61a5-112">例如，如果您只想要查看目前目錄中的檔案和資料夾名稱，也就是沒有其他資訊，例如檔案或資料夾的大小，或資料夾或資料夾的建立日期和時間。</span><span class="sxs-lookup"><span data-stu-id="b61a5-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="b61a5-113">在此情況下，您會在執行 dir 命令時附加 **/b** 引數：</span><span class="sxs-lookup"><span data-stu-id="b61a5-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="b61a5-114">當您包含 **/b** 引數時， **dir** 命令只會傳回目前目錄中的資料夾和檔案的名稱：</span><span class="sxs-lookup"><span data-stu-id="b61a5-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="b61a5-115">在上述命令中， **/b** 引數是將傳回的資料限制為檔案和資料夾名稱的唯一必要資訊。</span><span class="sxs-lookup"><span data-stu-id="b61a5-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="b61a5-116">使用命令列命令時，通常會發生這種情況：只有引數的實際存在，才能變更命令的行為。</span><span class="sxs-lookup"><span data-stu-id="b61a5-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="b61a5-117"> (也就是說，您可以包含 **/b** 引數以隱藏其他資訊，或排除 **/b** 引數以顯示額外的資訊。 ) 其他情況下，您必須指定 *引數值*。</span><span class="sxs-lookup"><span data-stu-id="b61a5-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="b61a5-118">引數值是傳遞給引數本身的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="b61a5-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="b61a5-119">例如， **/o** 引數可讓您指定您想要 dir 命令如何排序傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="b61a5-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="b61a5-120">在其他選項中，您可以使用引數值 **e** ，依副檔名或引數值 **s** 排序，依檔案大小排序。</span><span class="sxs-lookup"><span data-stu-id="b61a5-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="b61a5-121">例如，此命令會依照副檔名排序傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="b61a5-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="b61a5-122">請注意 **/o**引數後緊接著包含引數值**e**的方式：</span><span class="sxs-lookup"><span data-stu-id="b61a5-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="b61a5-123">使用我們的範例資料夾，傳回的資料會如下列所示，並依照副檔名排序：</span><span class="sxs-lookup"><span data-stu-id="b61a5-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="b61a5-124">或者，為了協助您準確指出我們所談論的專案：</span><span class="sxs-lookup"><span data-stu-id="b61a5-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="b61a5-125">雖然 Windows PowerShell 使用不同的術語，但使用 Windows PowerShell 的基本方法與使用命令視窗相同：您可以輸入命令，視需要包含引數和引數值，然後按 ENTER 執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="b61a5-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="b61a5-126">不過請注意，Windows PowerShell 會使用不同于命令介面所用的術語。</span><span class="sxs-lookup"><span data-stu-id="b61a5-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="b61a5-127">在 Windows PowerShell 中，您執行的命令稱為 *Cmdlet*。</span><span class="sxs-lookup"><span data-stu-id="b61a5-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="b61a5-128">接著，傳遞至 Cmdlet 的參數稱為 *參數*，傳遞給參數的值稱為 *參數值*。</span><span class="sxs-lookup"><span data-stu-id="b61a5-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="b61a5-129">前面的定義已有些簡化。</span><span class="sxs-lookup"><span data-stu-id="b61a5-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="b61a5-130">Cmdlet 基本上是迷你應用程式，只能在 Windows PowerShell 環境內執行。</span><span class="sxs-lookup"><span data-stu-id="b61a5-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="b61a5-131">不過，您也可以在 Windows PowerShell 中執行其他命令和應用程式，包括可以從命令視窗執行的大部分命令和應用程式。</span><span class="sxs-lookup"><span data-stu-id="b61a5-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="b61a5-132">例如，如果您想要在 Windows PowerShell 內啟動 [記事本]，您只需要輸入下列專案，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="b61a5-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="b61a5-133">不過，若要管理商務用 Skype Online，大部分系統管理員會依賴 Windows PowerShell Cmdlet 來執行系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="b61a5-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="b61a5-134">在時，有些其他類型的命令或應用程式可以用來管理商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="b61a5-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="b61a5-135">有時候，您可以使用商務用 Skype Online Cmdlet，而不需要任何其他引數 ( （如前文所述），引數稱為 Windows PowerShell) 中的參數。</span><span class="sxs-lookup"><span data-stu-id="b61a5-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="b61a5-136">例如，下列命令會呼叫沒有任何其他參數的 [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b61a5-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="b61a5-137">命令會傳回所有商務用 Skype Online 使用者的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b61a5-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="b61a5-138">不過，大部分商務用 Skype Online Cmdlet 也會接受 (和參數值) 的參數。</span><span class="sxs-lookup"><span data-stu-id="b61a5-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="b61a5-139">請考慮下列命令：</span><span class="sxs-lookup"><span data-stu-id="b61a5-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="b61a5-140">這個命令包含三個部分：</span><span class="sxs-lookup"><span data-stu-id="b61a5-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="b61a5-141">Cmdlet **Get-CsOnlineUser**。</span><span class="sxs-lookup"><span data-stu-id="b61a5-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="b61a5-142">Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="b61a5-142">The Identity parameter.</span></span> <span data-ttu-id="b61a5-143">請注意，在 Windows PowerShell 中，參數永遠會以破折號 ( ) 開頭。</span><span class="sxs-lookup"><span data-stu-id="b61a5-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="b61a5-144">這表示，針對這個相同的 Cmdlet，UnassignedUser 參數會使用下列語法來表示：</span><span class="sxs-lookup"><span data-stu-id="b61a5-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="b61a5-145">這有助於知道，不只是因為參數必須以短劃線開頭，但由於這與命令視窗不同，其引數是使用正斜線 (/) 開頭的：</span><span class="sxs-lookup"><span data-stu-id="b61a5-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="b61a5-146">參數值 **kenmyer@litwareinc.com**。</span><span class="sxs-lookup"><span data-stu-id="b61a5-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="b61a5-147">該命令會傳回特定使用者的資訊： identity 為 kenmyer@litwareinc.com 的使用者。</span><span class="sxs-lookup"><span data-stu-id="b61a5-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b61a5-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b61a5-148">See Also</span></span>


<span data-ttu-id="b61a5-149">[Windows PowerShell 和商務用 Skype Online 簡介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b61a5-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

