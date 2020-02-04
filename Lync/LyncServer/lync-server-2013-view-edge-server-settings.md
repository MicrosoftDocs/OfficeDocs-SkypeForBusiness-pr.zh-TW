---
title: Lync Server 2013：查看邊緣伺服器設定
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
ms.openlocfilehash: 6eaab70f2f6d651d6446aaa4a569277494b7a9ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="2811e-102">在 Lync Server 2013 中查看邊緣伺服器設定</span><span class="sxs-lookup"><span data-stu-id="2811e-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2811e-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="2811e-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="2811e-104">必須針對配置管理資料庫中的資料來審查一般邊緣伺服器設定，以協助保證所有變更都已按照已定義的變更控制程式進行記錄。</span><span class="sxs-lookup"><span data-stu-id="2811e-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="2811e-105">其他檢查可能包含下列各節所述的專案：</span><span class="sxs-lookup"><span data-stu-id="2811e-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="2811e-106">確認 [允許] 與 [封鎖] 清單</span><span class="sxs-lookup"><span data-stu-id="2811e-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="2811e-107">驗證聯盟網域的 SIP URI "Allow" 和 "Block" 清單，以判斷列出的命名空間是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="2811e-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="2811e-108">您可以使用 Windows PowerShell 來查看允許和封鎖的清單。</span><span class="sxs-lookup"><span data-stu-id="2811e-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="2811e-109">若要查看 [允許的網域] 清單上的網域，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="2811e-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="2811e-110">該命令會針對 [允許的網域] 清單上的網域傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="2811e-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="2811e-111">身分識別： contoso.com</span><span class="sxs-lookup"><span data-stu-id="2811e-111">Identity : contoso.com</span></span>

<span data-ttu-id="2811e-112">網域： contoso.com</span><span class="sxs-lookup"><span data-stu-id="2811e-112">Domain : contoso.com</span></span>

<span data-ttu-id="2811e-113">ProxyFqdn :</span><span class="sxs-lookup"><span data-stu-id="2811e-113">ProxyFqdn :</span></span>

<span data-ttu-id="2811e-114">評論</span><span class="sxs-lookup"><span data-stu-id="2811e-114">Comment :</span></span>

<span data-ttu-id="2811e-115">MarkForMonitoring： False</span><span class="sxs-lookup"><span data-stu-id="2811e-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="2811e-116">評論</span><span class="sxs-lookup"><span data-stu-id="2811e-116">Comment :</span></span>

<span data-ttu-id="2811e-117">若要查看 [封鎖的網域] 清單中的網域，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="2811e-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="2811e-118">接著，您將會收到針對每個封鎖網域的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="2811e-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="2811e-119">身分識別： tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="2811e-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="2811e-120">網域： tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="2811e-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="2811e-121">Windows PowerShell 也能讓您確認您可以連線到 [允許的網域] 清單中的網域。</span><span class="sxs-lookup"><span data-stu-id="2811e-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="2811e-122">例如，這個命令會驗證 Edge 伺服器（TargetFqdn）和聯盟網域 contoso.com 之間的連線：</span><span class="sxs-lookup"><span data-stu-id="2811e-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="2811e-123">這個命令會確認您的 Edge 伺服器與您在 [允許的網域] 清單中找到的所有網域之間的連線：</span><span class="sxs-lookup"><span data-stu-id="2811e-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="2811e-124">驗證多個邊緣伺服器相同</span><span class="sxs-lookup"><span data-stu-id="2811e-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="2811e-125">如果多個邊緣伺服器部署在負載均衡的陣列中，我們建議您驗證陣列中的所有邊緣伺服器是否都以相同的方式進行設定。</span><span class="sxs-lookup"><span data-stu-id="2811e-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="2811e-126">您可以在 [電腦管理] 管理單元的 Lync Server 2013 延伸的詳細資料窗格中，查看 Edge 伺服器的設定。</span><span class="sxs-lookup"><span data-stu-id="2811e-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2811e-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="2811e-127">See Also</span></span>


[<span data-ttu-id="2811e-128">CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="2811e-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="2811e-129">CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="2811e-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="2811e-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="2811e-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

