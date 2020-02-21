---
title: Lync Server 2013： 檢視 Edge Server 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c76eb9580c7ee394e0e60e5d0f8cfe38dcae65e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="a022c-102">在 Lync Server 2013 中檢視 Edge Server 設定</span><span class="sxs-lookup"><span data-stu-id="a022c-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a022c-103">_**上次修改主題：** 2014年-05-20 個_</span><span class="sxs-lookup"><span data-stu-id="a022c-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="a022c-104">一般 Edge Server 設定應該檢閱對組態管理資料庫中的資料，以協助確保所有變更所都記載依定義的變更控制程序。</span><span class="sxs-lookup"><span data-stu-id="a022c-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="a022c-105">額外檢查可能包括下列各節所述：</span><span class="sxs-lookup"><span data-stu-id="a022c-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="a022c-106">確認 [允許] 和 [封鎖清單</span><span class="sxs-lookup"><span data-stu-id="a022c-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="a022c-107">確認 SIP URI 「 允許 」 及 「 區塊 」 清單的同盟網域，以判斷是否列出命名空間仍然有效。</span><span class="sxs-lookup"><span data-stu-id="a022c-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="a022c-108">您可以使用 Windows PowerShell 來檢視允許和封鎖清單。</span><span class="sxs-lookup"><span data-stu-id="a022c-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="a022c-109">若要檢閱允許網域清單上的網域，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="a022c-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="a022c-110">該命令會傳回的資訊類似網域的允許網域清單上：</span><span class="sxs-lookup"><span data-stu-id="a022c-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="a022c-111">身分識別： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a022c-111">Identity : contoso.com</span></span>

<span data-ttu-id="a022c-112">網域： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a022c-112">Domain : contoso.com</span></span>

<span data-ttu-id="a022c-113">ProxyFqdn:</span><span class="sxs-lookup"><span data-stu-id="a022c-113">ProxyFqdn :</span></span>

<span data-ttu-id="a022c-114">註解：</span><span class="sxs-lookup"><span data-stu-id="a022c-114">Comment :</span></span>

<span data-ttu-id="a022c-115">MarkForMonitoring: False</span><span class="sxs-lookup"><span data-stu-id="a022c-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="a022c-116">註解：</span><span class="sxs-lookup"><span data-stu-id="a022c-116">Comment :</span></span>

<span data-ttu-id="a022c-117">若要檢閱封鎖的網域清單上的網域，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="a022c-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="a022c-118">接著，您會收到這每個封鎖的網域的資訊：</span><span class="sxs-lookup"><span data-stu-id="a022c-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="a022c-119">身分識別： tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="a022c-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="a022c-120">網域： tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="a022c-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="a022c-121">Windows PowerShell 也可讓您確認您可以連線到網域允許網域清單上。</span><span class="sxs-lookup"><span data-stu-id="a022c-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="a022c-122">例如，此命令會驗證您的 Edge Server (TargetFqdn) 與同盟的網域 contoso.com 之間的連線：</span><span class="sxs-lookup"><span data-stu-id="a022c-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="a022c-123">與此命令會驗證您的 Edge Server 與所有在您允許網域清單上找到的網域之間的連線：</span><span class="sxs-lookup"><span data-stu-id="a022c-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="a022c-124">確認 [多部 Edge Server 皆相同</span><span class="sxs-lookup"><span data-stu-id="a022c-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="a022c-125">如果負載平衡陣列中部署多部 Edge Server，建議您確認陣列中的所有 Edge Server 已都設定的方式相同。</span><span class="sxs-lookup"><span data-stu-id="a022c-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="a022c-126">在 [電腦管理] 嵌入式管理單元的 Lync Server 2013 副檔名的詳細資料窗格中，您可以檢視 Edge Server 的設定。</span><span class="sxs-lookup"><span data-stu-id="a022c-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a022c-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a022c-127">See Also</span></span>


[<span data-ttu-id="a022c-128">Get-csalloweddomain</span><span class="sxs-lookup"><span data-stu-id="a022c-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="a022c-129">Get-csblockeddomain</span><span class="sxs-lookup"><span data-stu-id="a022c-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="a022c-130">Test-csfederatedpartner</span><span class="sxs-lookup"><span data-stu-id="a022c-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

