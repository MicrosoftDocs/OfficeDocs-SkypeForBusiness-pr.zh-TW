---
title: 佈建要執行負載的拓撲
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08f9cd219e70f1f761ac49932b73ca0d8c618121
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="75fe7-102">佈建要執行負載的拓撲</span><span class="sxs-lookup"><span data-stu-id="75fe7-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75fe7-103">_**上次修改主題：** 2013年-02-04_</span><span class="sxs-lookup"><span data-stu-id="75fe7-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="75fe7-104">佈建要執行負載的拓撲</span><span class="sxs-lookup"><span data-stu-id="75fe7-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="75fe7-105">根據您現有的設定和 Lync Server 2013 的設定，您可能需要在您的環境中進行下列變更：</span><span class="sxs-lookup"><span data-stu-id="75fe7-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="75fe7-106">Windows PowerShell 執行原則設為 Unrestricted。</span><span class="sxs-lookup"><span data-stu-id="75fe7-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="75fe7-107">若要檢查您執行的原則設定，請開啟 [Lync Server 管理命令介面，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="75fe7-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="75fe7-108">如果此命令不會傳回值沒有限制，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="75fe7-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="75fe7-109">若要有效地設定 Lync Server 2013，您將需要：</span><span class="sxs-lookup"><span data-stu-id="75fe7-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="75fe7-110">熟悉 Lync Server 2013 拓撲 （例如，電腦名稱、 服務執行個體、 網站名稱及原則）。</span><span class="sxs-lookup"><span data-stu-id="75fe7-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="75fe7-111">例如群組 (例如，SIP Uri) 的回應群組搜尋，請將使用者至群組，所建立的部分。</span><span class="sxs-lookup"><span data-stu-id="75fe7-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="75fe7-112">若要從命令列執行指令碼，您可能會使用：</span><span class="sxs-lookup"><span data-stu-id="75fe7-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="75fe7-113">一般而言，其中此套件執行，從指令碼的產生追蹤中的指令碼將會儲存在從中上次叫用指令碼的相同路徑中的檔案之後，名為\<scriptname\>$h$m$s.txt。</span><span class="sxs-lookup"><span data-stu-id="75fe7-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="75fe7-114">例如，下午 12:15 執行 ArchivingPolicy.ps1</span><span class="sxs-lookup"><span data-stu-id="75fe7-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="75fe7-115">將產生的記錄檔，例如 ArchivingPolicy121500.txt。</span><span class="sxs-lookup"><span data-stu-id="75fe7-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="75fe7-116">最後，請注意，雖然我們所提供的範例，設定伺服器，但您負責修改或刪除組態完成執行負載之後。</span><span class="sxs-lookup"><span data-stu-id="75fe7-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

