---
title: Lync Server 2013：查看 Edge Server 設定
description: Lync Server 2013：查看 Edge Server 設定。
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
ms.openlocfilehash: 4318b8c97f53f267bb79953af504977f6437214d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569679"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="a8495-103">在 Lync Server 2013 中查看 Edge Server 設定</span><span class="sxs-lookup"><span data-stu-id="a8495-103">View Edge Server settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8495-104">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a8495-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="a8495-105">應該對照設定管理資料庫中的資料來複查一般 Edge Server 設定，以協助保證所有的變更都是根據定義的變更控制程式所記錄。</span><span class="sxs-lookup"><span data-stu-id="a8495-105">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="a8495-106">其他檢查可以包含下列各節所述的專案：</span><span class="sxs-lookup"><span data-stu-id="a8495-106">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="a8495-107">確認允許和封鎖清單</span><span class="sxs-lookup"><span data-stu-id="a8495-107">Verify the Allow and block lists</span></span>

<span data-ttu-id="a8495-108">請驗證同盟網域的 SIP URI 「允許」和「封鎖」清單，以判斷列出的命名空間是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="a8495-108">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="a8495-109">您可以使用 Windows PowerShell 來查看允許和封鎖的清單。</span><span class="sxs-lookup"><span data-stu-id="a8495-109">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="a8495-110">若要查看允許的網域清單上的網域，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="a8495-110">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="a8495-111">該命令會針對允許的網域清單上的網域，傳回類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="a8495-111">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="a8495-112">身分識別： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8495-112">Identity : contoso.com</span></span>

<span data-ttu-id="a8495-113">網域： contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8495-113">Domain : contoso.com</span></span>

<span data-ttu-id="a8495-114">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="a8495-114">ProxyFqdn :</span></span>

<span data-ttu-id="a8495-115">評論：</span><span class="sxs-lookup"><span data-stu-id="a8495-115">Comment :</span></span>

<span data-ttu-id="a8495-116">MarkForMonitoring： False</span><span class="sxs-lookup"><span data-stu-id="a8495-116">MarkForMonitoring : False</span></span>

<span data-ttu-id="a8495-117">評論：</span><span class="sxs-lookup"><span data-stu-id="a8495-117">Comment :</span></span>

<span data-ttu-id="a8495-118">若要查看封鎖的網域清單上的網域，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="a8495-118">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="a8495-119">接著，您將會收到每個封鎖網域的資訊，例如：</span><span class="sxs-lookup"><span data-stu-id="a8495-119">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="a8495-120">身分識別： tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="a8495-120">Identity : tailspintoys.com</span></span>

<span data-ttu-id="a8495-121">網域： tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="a8495-121">Domain : tailspintoys.com</span></span>

<span data-ttu-id="a8495-122">Windows PowerShell 也可讓您確認您可以連線至允許的網域清單上的網域。</span><span class="sxs-lookup"><span data-stu-id="a8495-122">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="a8495-123">例如，此命令會驗證 Edge Server (TargetFqdn) 與同盟網域 contoso.com 之間的連線：</span><span class="sxs-lookup"><span data-stu-id="a8495-123">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="a8495-124">而且，此命令會驗證您的 Edge Server 與允許的網域清單上的所有網域之間的連線：</span><span class="sxs-lookup"><span data-stu-id="a8495-124">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="a8495-125">驗證多部 Edge Server 相同</span><span class="sxs-lookup"><span data-stu-id="a8495-125">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="a8495-126">如果有多部 Edge Server 部署在負載平衡陣列中，建議您驗證陣列中的所有 Edge Server 都是以相同的方式來設定。</span><span class="sxs-lookup"><span data-stu-id="a8495-126">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="a8495-127">您可以在 [電腦管理] 嵌入式管理單元的 Lync Server 2013 擴充功能的詳細資料窗格中，查看 Edge server 的設定。</span><span class="sxs-lookup"><span data-stu-id="a8495-127">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8495-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a8495-128">See Also</span></span>


[<span data-ttu-id="a8495-129">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="a8495-129">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="a8495-130">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="a8495-130">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="a8495-131">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="a8495-131">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

