---
title: 執行 LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325a3dab058132dfe6bbf8558ebe771450f36ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a><span data-ttu-id="fe4b3-102">執行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="fe4b3-102">Run LyncPerfTool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe4b3-103">_**上次修改主題：** 2013年-02-24_</span><span class="sxs-lookup"><span data-stu-id="fe4b3-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="fe4b3-104">在執行之前 [Lync Server 2013 壓力及效能工具 (LyncPerfTool.exe)，您必須建立使用者、 連絡人及案例。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-104">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="fe4b3-105">如需使用工具來執行這些動作的詳細資訊，請參閱[建立使用者和連絡人](create-users-and-contacts.md)和[設定使用者設定檔](configure-user-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-105">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="fe4b3-106">執行這些工具也會產生檔案所用執行身分批次檔案的一部分的 LyncPerfTool.exe 包含必要參數。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-106">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="fe4b3-107">執行 Lync Server 2013 壓力及效能工具</span><span class="sxs-lookup"><span data-stu-id="fe4b3-107">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="fe4b3-108">UserProfileGenerator.exe 工具建立批次檔案，可讓您執行 LyncPerfTool.exe 註冊 LyncPerfTool 效能計數器和載入 XML 組態檔。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-108">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="fe4b3-109">批次檔案執行每個設定檔 LyncPerfTool.exe 一個執行個體。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-109">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="fe4b3-110">若要執行的批次檔案，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fe4b3-110">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="fe4b3-111">複製資料夾包含的設定資料夾和檔案至 LyncStressTool.exe 包含每個用戶端電腦的目錄。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-111">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="fe4b3-112">(例如，如果名為 1.28 資料夾中產生的組態檔\_13.16.16，將該資料夾複製到包含 LyncPerfTool.exe 每個用戶端的資料夾。)</span><span class="sxs-lookup"><span data-stu-id="fe4b3-112">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="fe4b3-113">瀏覽至適當編號的用戶端資料夾並執行 RunClient 批次指令碼。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-113">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="fe4b3-114">您可以只連按兩下 [Windows 檔案總管] 中的批次檔案，它會執行所有的組態檔，該用戶端數目。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-114">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="fe4b3-115">您也可以從適當的用戶端資料夾執行指令碼，使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="fe4b3-115">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="fe4b3-116">若要直接執行 LyncPerfTool.exe，開啟命令提示字元，則請在命令列輸入下列命令 (當第一次這麼做，請務必將註冊為稍後此 topic):LyncPerfTool.exe /file 附註中顯示的效能計數器 regsvr32 /i /n /s LyncPerfToolPerf.dll，：\<configXML\></span><span class="sxs-lookup"><span data-stu-id="fe4b3-116">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="fe4b3-117">若要有工具顯示設定檔案中的值會包含 /displayfile 參數在上述命令，就像這樣：</span><span class="sxs-lookup"><span data-stu-id="fe4b3-117">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="fe4b3-118">若要結束程序，請按 Ctrl + C。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-118">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe4b3-119">在執行之前 LyncPerfTool 直接，您必須註冊的效能計數器。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-119">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="fe4b3-120">輸入下列命令，以登錄效能計數器：</span><span class="sxs-lookup"><span data-stu-id="fe4b3-120">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="fe4b3-121">每個執行個體開始的 LyncPerfTool.exe 會立即啟動登入使用者，通常是一位使用者每秒的速率。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-121">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="fe4b3-122">尖峰使用者登入率的集區是大約每秒的 12。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-122">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="fe4b3-123">這表示，您應該不啟動超過 12 個 LyncPerfTool 執行個體同時，雖然使用者仍登入。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-123">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="fe4b3-124">1000 個使用者將會完全在一秒登入，需要約 20 分鐘。</span><span class="sxs-lookup"><span data-stu-id="fe4b3-124">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe4b3-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fe4b3-125">See Also</span></span>


[<span data-ttu-id="fe4b3-126">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="fe4b3-126">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="fe4b3-127">設定使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="fe4b3-127">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

