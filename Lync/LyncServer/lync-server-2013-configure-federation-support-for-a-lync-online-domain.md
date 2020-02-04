---
title: Lync Server 2013：針對 Lync Online 網域設定同盟支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="e7a79-102">在 Lync Server 2013 中設定 Lync Online 網域的同盟支援</span><span class="sxs-lookup"><span data-stu-id="e7a79-102">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7a79-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e7a79-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e7a79-104">使用 Microsoft Lync Online 2010 客戶進行聯盟，必須完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e7a79-104">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="e7a79-105">針對 Lync Online 2010 客戶的網域設定支援（例如，contoso.onmicrosoft.com）。</span><span class="sxs-lookup"><span data-stu-id="e7a79-105">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="e7a79-106">根據在本檔的[Lync Server 2013 區段中與 Lync Online 客戶進行聯盟的先決條件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)，您應該已經針對您的組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="e7a79-106">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="e7a79-107">啟用同盟時，必須指定要用來控制聯盟網域存取權的方法。</span><span class="sxs-lookup"><span data-stu-id="e7a79-107">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="e7a79-108">如果您將組織設定為使用 [探索]，將網域新增到貴組織的 [允許] 清單是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="e7a79-108">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="e7a79-109">如果您沒有啟用網域探索，您必須將 Lync Online 客戶的功能變數名稱新增至 [允許的網域] 清單。</span><span class="sxs-lookup"><span data-stu-id="e7a79-109">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="e7a79-110">您可以使用 Lync Server [控制台] 或執行**新的 CSAllowedDomain** Cmdlet 來新增功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="e7a79-110">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="e7a79-111">如需使用 Lync Server [控制台] 的詳細資料，包括啟用網域探索，請參閱在作業檔中[管理您的組織在 Lync Server 2013 中的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="e7a79-111">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="e7a79-112">如需使用**CSAllowedDomain** Cmdlet 來新增網域的詳細資料，請參閱 [作業] 檔中的 [[新增-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) ]。</span><span class="sxs-lookup"><span data-stu-id="e7a79-112">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7a79-113">Lync Online 客戶可以有多個網域。</span><span class="sxs-lookup"><span data-stu-id="e7a79-113">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="e7a79-114">如果您想要與一個以上的網域聯盟，您必須針對每一個您要支援同盟的網域設定支援，而且 Lync Online 客戶的管理員必須針對每一個要進行聯盟的網域啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="e7a79-114">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="e7a79-115">針對您要與其聯盟的 Lync Online 2010 客戶網域，設定其主機服務提供者支援。</span><span class="sxs-lookup"><span data-stu-id="e7a79-115">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="e7a79-116">使用本節中的程式來設定託管提供者的支援。</span><span class="sxs-lookup"><span data-stu-id="e7a79-116">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7a79-117">此步驟僅適用于具備 Lync Online 客戶網域的同盟，不適用於與在聯盟夥伴位置上部署之任何網域的同盟。</span><span class="sxs-lookup"><span data-stu-id="e7a79-117">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="e7a79-118">若要設定主機服務提供者的支援</span><span class="sxs-lookup"><span data-stu-id="e7a79-118">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="e7a79-119">從前端伺服器，啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e7a79-119">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7a79-120">執行**新的 CsHostingProvider** Cmdlet 來建立及設定主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="e7a79-120">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="e7a79-121">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="e7a79-121">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="e7a79-122">上述範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="e7a79-122">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="e7a79-123">身分**識別**會為您建立的主機服務提供者指定唯一的字串值識別碼。</span><span class="sxs-lookup"><span data-stu-id="e7a79-123">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="e7a79-124">請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。</span><span class="sxs-lookup"><span data-stu-id="e7a79-124">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="e7a79-125">**ProxyFQDN**指定主機提供者所使用之 proxy 伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="e7a79-125">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="e7a79-126">您無法修改此值。</span><span class="sxs-lookup"><span data-stu-id="e7a79-126">This value cannot be modified.</span></span> <span data-ttu-id="e7a79-127">如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。</span><span class="sxs-lookup"><span data-stu-id="e7a79-127">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="e7a79-128">**VerificationLevel**指定如何驗證從主機託管提供者傳送的訊息（或 if），以確保它們已從該提供者傳送。</span><span class="sxs-lookup"><span data-stu-id="e7a79-128">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="e7a79-p107">\*\*Enabled \*\* 指出網域與裝載提供者之間的網路連線是否已啟用。只有將此值設為 \*\*True \*\*，才能在兩個組織之間交換訊息。</span><span class="sxs-lookup"><span data-stu-id="e7a79-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="e7a79-131">\*\*EnabledSharedAddressSpace \*\* 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。</span><span class="sxs-lookup"><span data-stu-id="e7a79-131">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="e7a79-132">**HostsOCSUsers**表示主機服務提供者是否用來託管 Lync Server 帳戶。</span><span class="sxs-lookup"><span data-stu-id="e7a79-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="e7a79-133">如果為 \*\*False \*\*，則提供者會裝載其他帳戶類型，例如 Microsoft Exchange 帳戶。</span><span class="sxs-lookup"><span data-stu-id="e7a79-133">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="e7a79-134">**IsLocal** ：指示主機服務提供者所使用的 proxy 伺服器是否包含在您的 Lync server 拓撲中。</span><span class="sxs-lookup"><span data-stu-id="e7a79-134">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="e7a79-135">如需有關使用此 Cmdlet 的詳細資訊，請參閱作業檔中的[新 CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 。</span><span class="sxs-lookup"><span data-stu-id="e7a79-135">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

