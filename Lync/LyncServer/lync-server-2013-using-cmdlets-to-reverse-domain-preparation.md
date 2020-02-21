---
title: Lync Server 2013： 使用 cmdlet 來反轉網域準備
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
ms.openlocfilehash: ac26e17ad9e0ab13529da438bc2e12bec210808d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="fd142-102">使用 cmdlet 來反轉網域準備 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd142-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd142-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="fd142-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="fd142-104">使用 **Disable-CsAdDomain** Cmdlet 來反轉網域準備步驟。</span><span class="sxs-lookup"><span data-stu-id="fd142-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="fd142-105">若要使用 Cmdlet 來反轉網域準備</span><span class="sxs-lookup"><span data-stu-id="fd142-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="fd142-106">以 Domain Admins 群組成員的身分登入網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd142-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="fd142-107">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="fd142-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fd142-108">執行：</span><span class="sxs-lookup"><span data-stu-id="fd142-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="fd142-109">例如：</span><span class="sxs-lookup"><span data-stu-id="fd142-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="fd142-110">Force 參數已存在，如果復原網域準備工作後，即使一或多個前端伺服器或 A / V 會議伺服器中的網域就會啟動。</span><span class="sxs-lookup"><span data-stu-id="fd142-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="fd142-111">如果有的話，如果 Force 參數不存在，會終止網域準備復原前端伺服器或 A / V 會議伺服器中的網域就會啟動。</span><span class="sxs-lookup"><span data-stu-id="fd142-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd142-112">GlobalSettingsDomainController 參數可讓您指出通用設定的存放位置。</span><span class="sxs-lookup"><span data-stu-id="fd142-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="fd142-113">如果您的設定存放在 System 容器 (在升級部署作業期間，當通用設定尚未移轉到 Configuration 容器時的常見現象)，請將網域控制站定義到 Active Directory 樹系根目錄中。</span><span class="sxs-lookup"><span data-stu-id="fd142-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="fd142-114">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="fd142-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="fd142-115">如果您未指定此參數，指令程式會假設此設定會儲存在 [Configuration] 容器，且所參照的任何網域控制站 AD&nbsp;DS。</span><span class="sxs-lookup"><span data-stu-id="fd142-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd142-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fd142-116">See Also</span></span>


[<span data-ttu-id="fd142-117">執行網域準備 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd142-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="fd142-118">Lync Server 2013 的準備網域</span><span class="sxs-lookup"><span data-stu-id="fd142-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

