---
title: Lync Server 2013：開始將使用者從 Lync Online 移植到 Lync 內部部署之前的第一個步驟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59ca20a994934a199504a4fb6a7dd5eec206c960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="5294b-102">在 Lync Server 2013 中開始將使用者從 Lync Online 移植到 Lync 內部部署之前的第一個步驟</span><span class="sxs-lookup"><span data-stu-id="5294b-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5294b-103">_**主題上次修改日期：** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="5294b-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="5294b-104">在您開始將 Lync Online 使用者移至您的內部部署環境之前，請先檢查下列所有專案是否屬實：</span><span class="sxs-lookup"><span data-stu-id="5294b-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="5294b-105">您的 Lync Server 內部部署環境必須完全部署並驗證。</span><span class="sxs-lookup"><span data-stu-id="5294b-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="5294b-106">如需詳細資訊，請參閱[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5294b-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="5294b-107">您的 Lync Online 租使用者必須針對遠端 PowerShell 存取進行設定。</span><span class="sxs-lookup"><span data-stu-id="5294b-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="5294b-108">若要這樣做，請先安裝適用于 Windows PowerShell 的 Lync Online 模組，您可以在[http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)這裡找到：。</span><span class="sxs-lookup"><span data-stu-id="5294b-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="5294b-109">安裝模組之後，您可以在 Lync Server 管理命令介面中輸入下列 Cmdlet 來建立遠端會話：</span><span class="sxs-lookup"><span data-stu-id="5294b-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    <span data-ttu-id="5294b-110">如需有關如何使用 Lync Online 建立遠端 PowerShell 會話的詳細資訊，請參閱[使用 Windows PowerShell 連線至 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5294b-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="5294b-111">如需使用 Lync Online PowerShell 模組的詳細資訊，請參閱[使用 Windows PowerShell 管理 Lync online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5294b-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="5294b-112">您的 Lync Online 必須針對共用的 SIP 位址空間進行設定。</span><span class="sxs-lookup"><span data-stu-id="5294b-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="5294b-113">若要這樣做，請先使用 Lync Online 啟動遠端 Powershell 會話。</span><span class="sxs-lookup"><span data-stu-id="5294b-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="5294b-114">然後執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5294b-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="5294b-115">完成這些步驟之後，您可以移至將[Lync Online 使用者遷移至 Lync Server 2013 中的 lync 內部部署](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="5294b-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

