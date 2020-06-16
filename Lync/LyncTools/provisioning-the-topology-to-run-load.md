---
title: 布建要執行負載的拓撲
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3e08a66397e5c6e7fb5b6111fbdcf6d11d3632a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="dc8df-102">布建要執行負載的拓撲</span><span class="sxs-lookup"><span data-stu-id="dc8df-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc8df-103">_**主題上次修改日期：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="dc8df-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="dc8df-104">布建要執行負載的拓撲</span><span class="sxs-lookup"><span data-stu-id="dc8df-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="dc8df-105">根據您現有的 Lync Server 2013 設定和設定，您可能需要在您的環境中進行下列變更：</span><span class="sxs-lookup"><span data-stu-id="dc8df-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="dc8df-106">設定 Windows PowerShell 執行原則為無限制。</span><span class="sxs-lookup"><span data-stu-id="dc8df-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="dc8df-107">若要檢查您的執行原則設定，請開啟 Lync Server 管理命令介面，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dc8df-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="dc8df-108">如果此命令不會傳回無限制的值，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dc8df-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="dc8df-109">若要有效地設定 Lync Server 2013，您將需要：</span><span class="sxs-lookup"><span data-stu-id="dc8df-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="dc8df-110">熟悉 Lync Server 2013 拓撲（例如，電腦名稱稱、服務實例、網站名稱和原則）。</span><span class="sxs-lookup"><span data-stu-id="dc8df-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="dc8df-111">將一些已建立的使用者指派給群組，例如回應群組搜尋群組（例如，SIP URIs）。</span><span class="sxs-lookup"><span data-stu-id="dc8df-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="dc8df-112">若要從命令列執行腳本，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="dc8df-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="dc8df-113">在此套件中的其中一個腳本執行完畢之後，腳本所產生的追蹤將會儲存在用來呼叫腳本的相同路徑中，名為 \<scriptname\> $h $ m $s.txt。</span><span class="sxs-lookup"><span data-stu-id="dc8df-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="dc8df-114">例如，在 12:15 P.M. 執行 ArchivingPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="dc8df-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="dc8df-115">會產生記錄檔，例如 ArchivingPolicy121500.txt。</span><span class="sxs-lookup"><span data-stu-id="dc8df-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="dc8df-116">最後，請注意，雖然我們提供了設定伺服器的範例，但您會在完成執行負載後，負責修改或刪除設定。</span><span class="sxs-lookup"><span data-stu-id="dc8df-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

