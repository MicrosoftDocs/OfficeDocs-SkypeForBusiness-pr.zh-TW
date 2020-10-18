---
title: Lync Server 2013：使用 Cmdlet 進行反向網域準備
description: Lync Server 2013：使用 Cmdlet 進行反向網域準備。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d26cc97ee934ee959838f38f4e2f52f9bf89566
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580409"
---
# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="e4e3a-103">使用 Cmdlet 進行 Lync Server 2013 的反向網域準備</span><span class="sxs-lookup"><span data-stu-id="e4e3a-103">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4e3a-104">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e4e3a-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e4e3a-105">使用 **Disable-CsAdDomain** Cmdlet 來反轉網域準備步驟。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-105">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="e4e3a-106">若要使用 Cmdlet 來反轉網域準備</span><span class="sxs-lookup"><span data-stu-id="e4e3a-106">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="e4e3a-107">以 Domain Admins 群組成員的身分登入網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-107">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="e4e3a-108">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e4e3a-109">運行：</span><span class="sxs-lookup"><span data-stu-id="e4e3a-109">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="e4e3a-110">例如：</span><span class="sxs-lookup"><span data-stu-id="e4e3a-110">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="e4e3a-111">如果 Force 參數存在，即使已啟動網域中的一或多部前端伺服器或 A/V 會議伺服器，也會還原網域準備。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-111">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="e4e3a-112">如果 Force 參數不存在，則會在啟用網域中的任何前端伺服器或 A/V 的會議服務器之後終止網域準備復原。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-112">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4e3a-113">GlobalSettingsDomainController 參數可讓您指出通用設定的存放位置。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-113">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="e4e3a-114">如果您的設定存放在 System 容器 (在升級部署作業期間，當通用設定尚未移轉到 Configuration 容器時的常見現象)，請將網域控制站定義到 Active Directory 樹系根目錄中。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-114">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="e4e3a-115">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-115">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="e4e3a-116">如果您未指定此參數，則指令程式會假設設定會儲存在設定容器中，並參照 AD DS 中的任何網域控制站 &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="e4e3a-116">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4e3a-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e4e3a-117">See Also</span></span>


[<span data-ttu-id="e4e3a-118">對 Lync Server 2013 執行網域準備</span><span class="sxs-lookup"><span data-stu-id="e4e3a-118">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="e4e3a-119">準備 Lync Server 2013 的網域</span><span class="sxs-lookup"><span data-stu-id="e4e3a-119">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

