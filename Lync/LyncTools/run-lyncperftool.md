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
ms.openlocfilehash: 29a36be8c6703dad52e6c36d363ae23013643bd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a><span data-ttu-id="a1d2c-102">執行 LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="a1d2c-102">Run LyncPerfTool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1d2c-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a1d2c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a1d2c-104">在執行 Lync Server 2013 的應力和效能工具（LyncPerfTool）之前，您必須建立使用者、連絡人和案例。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-104">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="a1d2c-105">如需使用工具執行這些動作的詳細資料，請參閱[建立使用者和連絡人](create-users-and-contacts.md)及[設定使用者設定檔](configure-user-profile.md)。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-105">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="a1d2c-106">執行這些工具也會產生一個檔案，該檔案會以包含所需參數的批次檔案的一部分來執行 LyncPerfTool。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-106">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="a1d2c-107">執行 Lync Server 2013 應力和效能工具</span><span class="sxs-lookup"><span data-stu-id="a1d2c-107">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="a1d2c-108">UserProfileGenerator 工具會建立可讓您執行 LyncPerfTool 的批次處理檔案，方法是註冊 LyncPerfTool 效能計數器並載入 XML 設定檔。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-108">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="a1d2c-109">批次處理檔案會針對每個設定檔執行 LyncPerfTool 的一個實例。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-109">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="a1d2c-110">若要執行批次檔案，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a1d2c-110">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="a1d2c-111">將包含配置資料夾和檔案的資料夾，複製到每個用戶端電腦上包含 LyncStressTool 的目錄。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-111">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="a1d2c-112">（例如，如果您在名為 1.28\_13.16.16 的資料夾中產生了設定檔案，請將該資料夾複製到每個用戶端上包含 LyncPerfTool 的資料夾）。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-112">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="a1d2c-113">流覽至適當編號的用戶端資料夾，並執行 RunClient 批次腳本。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-113">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="a1d2c-114">您只要在 Windows 資源管理器中按兩下批次檔案，該檔案就會針對該用戶端編號執行所有設定檔案。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-114">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="a1d2c-115">您也可以使用下列語法，在適當的用戶端資料夾中執行腳本：</span><span class="sxs-lookup"><span data-stu-id="a1d2c-115">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="a1d2c-116">若要直接執行 LyncPerfTool，請開啟命令提示字元，然後在命令列中輸入下列命令（第一次執行此動作時，請務必註冊效能計數器 regsvr32/i/i/n LyncPerfToolPerf，如本主題稍後所示的筆記所示）： LyncPerfTool/file：\<configXML\></span><span class="sxs-lookup"><span data-stu-id="a1d2c-116">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="a1d2c-117">若要讓工具顯示設定檔中的值，請在前面的命令中包含/displayfile 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a1d2c-117">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="a1d2c-118">若要結束處理常式，請按 Ctrl + C。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-118">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1d2c-119">在直接執行 LyncPerfTool 之前，您必須先註冊效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-119">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="a1d2c-120">輸入下列命令來註冊效能計數器：</span><span class="sxs-lookup"><span data-stu-id="a1d2c-120">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="a1d2c-121">您開始的每個 LyncPerfTool 實例都會立即開始登入使用者，通常是每秒一個使用者的速率。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-121">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="a1d2c-122">該池的使用者登入速率峰值，大約每秒12次。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-122">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="a1d2c-123">這表示您不應該同時啟動超過12個 LyncPerfTool 實例，而使用者仍在登入。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-123">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="a1d2c-124">1000使用者大約需要20分鐘的時間才能完全登入（每秒一個）。</span><span class="sxs-lookup"><span data-stu-id="a1d2c-124">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1d2c-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="a1d2c-125">See Also</span></span>


[<span data-ttu-id="a1d2c-126">建立使用者和連絡人</span><span class="sxs-lookup"><span data-stu-id="a1d2c-126">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="a1d2c-127">設定使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="a1d2c-127">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

