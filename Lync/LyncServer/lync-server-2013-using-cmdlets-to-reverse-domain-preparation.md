---
title: Lync Server 2013：將 Cmdlet 用於反向網域準備
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
ms.openlocfilehash: d72c135e7daccd677f8e42ea93a2aace8d7cafb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="da96b-102">將 Cmdlet 用於 Lync Server 2013 的反向網域準備</span><span class="sxs-lookup"><span data-stu-id="da96b-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da96b-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="da96b-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="da96b-104">使用**Disable CsAdDomain** Cmdlet 來反轉網域準備步驟。</span><span class="sxs-lookup"><span data-stu-id="da96b-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="da96b-105">使用 Cmdlet 來反向網域準備</span><span class="sxs-lookup"><span data-stu-id="da96b-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="da96b-106">以網域系統管理員群組的成員身分登入網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="da96b-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="da96b-107">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="da96b-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="da96b-108">用盡</span><span class="sxs-lookup"><span data-stu-id="da96b-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="da96b-109">例如：</span><span class="sxs-lookup"><span data-stu-id="da96b-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="da96b-110">如果 Force 參數存在，即使已啟用網域中的一或多個前端伺服器或 A/V 會議伺服器，也會回滾網域準備。</span><span class="sxs-lookup"><span data-stu-id="da96b-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="da96b-111">如果 Force 參數不存在，則在啟用網域中的任何前端伺服器或 A/V 會議伺服器之後，就會終止網域準備復原。</span><span class="sxs-lookup"><span data-stu-id="da96b-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da96b-112">[參數 GlobalSettingsDomainController] 可讓您指出儲存全域設定的位置。</span><span class="sxs-lookup"><span data-stu-id="da96b-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="da96b-113">如果您的設定是儲存在系統容器中（這通常是使用未將全域設定遷移至配置容器的升級部署），您可以在 Active Directory 目錄林的根目錄中定義網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="da96b-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="da96b-114">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="da96b-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="da96b-115">如果您沒有指定此參數，Cmdlet 會假設設定會儲存在配置容器中，並參照 AD&nbsp;DS 中的任何網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="da96b-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da96b-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="da96b-116">See Also</span></span>


[<span data-ttu-id="da96b-117">為 Lync Server 2013 執行網域準備</span><span class="sxs-lookup"><span data-stu-id="da96b-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="da96b-118">針對 Lync Server 2013 準備網域</span><span class="sxs-lookup"><span data-stu-id="da96b-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

