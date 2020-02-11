---
title: 商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數及參數值
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9fadf59b353458b2e7c48f597c11b92342e7edc
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="25aee-102">商務用 Skype Online 中的 Windows PowerShell Cmdlet、參數及參數值</span><span class="sxs-lookup"><span data-stu-id="25aee-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25aee-103">_**主題上次修改日期：** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="25aee-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="25aee-104">如果您熟悉在所有 Windows 版本（或您熟悉 MS-DOS）中找到的命令視窗，當您瞭解如何使用 Windows PowerShell 時，就會開始進行。</span><span class="sxs-lookup"><span data-stu-id="25aee-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="25aee-105">在命令視窗中，您可以輸入命令，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="25aee-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="25aee-106">在 [回應] 中，電腦會執行命令或可執行檔。</span><span class="sxs-lookup"><span data-stu-id="25aee-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="25aee-107">例如，若要傳回目前目錄中所有檔案和資料夾的相關資訊，請在命令提示字元輸入這個命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="25aee-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="25aee-108">接著，您會傳回目前目錄中所有檔案和資料夾的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="25aee-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="25aee-109">當您只輸入命令或可執行檔的名稱時，這就是結果的一個範例。</span><span class="sxs-lookup"><span data-stu-id="25aee-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="25aee-110">不過，在命令視窗中執行的許多命令也會接受*引數*。</span><span class="sxs-lookup"><span data-stu-id="25aee-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="25aee-111">引數是傳遞至命令的其他資訊，可修改命令的行為。</span><span class="sxs-lookup"><span data-stu-id="25aee-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="25aee-112">例如，如果您只想在目前目錄中看到檔案和資料夾的名稱，就不會有其他資訊（例如檔案或資料夾的大小），或是資料夾或資料夾的建立日期和時間。</span><span class="sxs-lookup"><span data-stu-id="25aee-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="25aee-113">在這種情況下，執行 dir 命令時，會附加 **/b**引數：</span><span class="sxs-lookup"><span data-stu-id="25aee-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="25aee-114">當您包含 **/b**引數時， **dir**命令只會傳回目前目錄中所找到之資料夾和檔案的名稱：</span><span class="sxs-lookup"><span data-stu-id="25aee-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="25aee-115">在上述命令中， **/b**引數是將傳回的資料限制為檔案和資料夾名稱所需的唯一資訊。</span><span class="sxs-lookup"><span data-stu-id="25aee-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="25aee-116">使用命令列命令時，通常會發生這種情況：只是變更命令列為所需的引數狀態。</span><span class="sxs-lookup"><span data-stu-id="25aee-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="25aee-117">（也就是說，您包含 **/b**引數以隱藏其他資訊，或排除 **/b**引數以顯示額外的資訊。）不過，在其他時間，您必須指定*引數值*。</span><span class="sxs-lookup"><span data-stu-id="25aee-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="25aee-118">引數值是傳遞給引數本身的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="25aee-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="25aee-119">例如， **/o**引數可讓您指定 dir 命令排序傳回資料的方式。</span><span class="sxs-lookup"><span data-stu-id="25aee-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="25aee-120">在其他選項中，您可以使用引數值**e**來依據檔案副檔名或引數值**s**來排序（依檔案大小排序）。</span><span class="sxs-lookup"><span data-stu-id="25aee-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="25aee-121">例如，這個命令會依副檔名來排序傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="25aee-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="25aee-122">請注意在 **/o**引數後面立即包含引數值**e**的方式：</span><span class="sxs-lookup"><span data-stu-id="25aee-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="25aee-123">使用我們的範例資料夾，傳回的資料看起來會像這樣，而這些檔案會依副檔名字母順序排序：</span><span class="sxs-lookup"><span data-stu-id="25aee-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="25aee-124">或者，協助您精確找出我們所談論的專案：</span><span class="sxs-lookup"><span data-stu-id="25aee-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="25aee-125">雖然 Windows PowerShell 使用不同的術語，但使用 Windows PowerShell 的基本方法與使用命令視窗相同：您可以輸入命令，視需要包含引數和引數值，然後按 ENTER 執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="25aee-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="25aee-126">不過請注意，Windows PowerShell 所使用的術語與命令外殼程式使用的不同。</span><span class="sxs-lookup"><span data-stu-id="25aee-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="25aee-127">在 Windows PowerShell 中，您執行的命令稱為*Cmdlet*。</span><span class="sxs-lookup"><span data-stu-id="25aee-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="25aee-128">接著，傳遞到 Cmdlet 的引數稱為*參數*，傳遞給參數的值稱為*參數值*。</span><span class="sxs-lookup"><span data-stu-id="25aee-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="25aee-129">前面的定義比較簡單。</span><span class="sxs-lookup"><span data-stu-id="25aee-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="25aee-130">Cmdlet 實質上是迷你應用程式，只能在 Windows PowerShell 環境中執行。</span><span class="sxs-lookup"><span data-stu-id="25aee-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="25aee-131">不過，您也可以在 Windows PowerShell 中執行其他命令和應用程式，包括大多數可從命令視窗執行的命令和應用程式。</span><span class="sxs-lookup"><span data-stu-id="25aee-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="25aee-132">例如，如果您想要從 Windows PowerShell 中啟動記事本，您只需輸入以下內容，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="25aee-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="25aee-133">不過，在管理商務用 Skype Online 時，大部分的系統管理員都會依賴 Windows PowerShell Cmdlet 來執行系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="25aee-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="25aee-134">一次，有幾種其他類型的命令或應用程式可用來管理商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="25aee-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="25aee-135">有時候，您不需要任何其他引數就能使用商務用 Skype Online Cmdlet （如所述，引數稱為 Windows PowerShell 中的參數）。</span><span class="sxs-lookup"><span data-stu-id="25aee-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="25aee-136">例如，下列命令會呼叫不含任何其他參數的[CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25aee-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="25aee-137">根據其本身，該命令會傳回您所有商務用 Skype Online 使用者的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="25aee-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="25aee-138">不過，大部分的商務用 Skype Online Cmdlet 也會接受參數（和參數值）。</span><span class="sxs-lookup"><span data-stu-id="25aee-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="25aee-139">請考慮下列命令：</span><span class="sxs-lookup"><span data-stu-id="25aee-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="25aee-140">這個命令包含三個部分：</span><span class="sxs-lookup"><span data-stu-id="25aee-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="25aee-141">Cmdlet **CsOnlineUser**。</span><span class="sxs-lookup"><span data-stu-id="25aee-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="25aee-142">身分識別參數。</span><span class="sxs-lookup"><span data-stu-id="25aee-142">The Identity parameter.</span></span> <span data-ttu-id="25aee-143">請注意，在 Windows PowerShell 中，參數總是以破折號（-）開頭。</span><span class="sxs-lookup"><span data-stu-id="25aee-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="25aee-144">也就是說，對於這個相同的 Cmdlet，會使用下列語法來指示 UnassignedUser 參數：</span><span class="sxs-lookup"><span data-stu-id="25aee-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="25aee-145">這個方法很有用，不只是因為參數必須以破折號開頭，也可能是因為這與命令視窗不同，其中的引數是使用正斜線（/）開頭的：</span><span class="sxs-lookup"><span data-stu-id="25aee-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="25aee-146">參數值**kenmyer@litwareinc.com**。</span><span class="sxs-lookup"><span data-stu-id="25aee-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="25aee-147">這個指令會傳回特定使用者的相關資訊： kenmyer@litwareinc.com 身分識別的使用者。</span><span class="sxs-lookup"><span data-stu-id="25aee-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="25aee-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="25aee-148">See Also</span></span>


<span data-ttu-id="25aee-149">[Windows PowerShell 與 Lync Online 的簡介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="25aee-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

