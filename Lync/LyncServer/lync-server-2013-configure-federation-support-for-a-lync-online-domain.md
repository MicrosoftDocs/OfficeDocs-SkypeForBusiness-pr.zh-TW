---
title: Lync Server 2013：設定 Lync Online 網域的同盟支援
description: Lync Server 2013：設定 Lync Online 網域的同盟支援。
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
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553299"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="cc960-103">在 Lync Server 2013 中設定 Lync Online 網域的同盟支援</span><span class="sxs-lookup"><span data-stu-id="cc960-103">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc960-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cc960-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cc960-105">與 Microsoft Lync Online 2010 客戶同盟需要您完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cc960-105">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="cc960-106">為 Lync Online 2010 客戶 (的網域設定支援，例如，contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="cc960-106">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="cc960-107">如您在本檔的 [與 lync Online 客戶進行同盟的 [必要條件2013中](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) 所指定，您應該已經為您的組織啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="cc960-107">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="cc960-108">啟用同盟需要指定同盟網域用來控制存取的方法。</span><span class="sxs-lookup"><span data-stu-id="cc960-108">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="cc960-109">如果您將組織設定成使用探索，則可選擇是否將網域新增至組織的允許清單中。</span><span class="sxs-lookup"><span data-stu-id="cc960-109">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="cc960-110">如果您未啟用網域探索，您必須將 Lync Online 客戶的功能變數名稱新增至您的允許網域清單。</span><span class="sxs-lookup"><span data-stu-id="cc960-110">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="cc960-111">您可以使用 Lync Server 控制台或執行 **CSAllowedDomain** Cmdlet 來新增功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cc960-111">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="cc960-112">如需使用 Lync Server 控制台（包括啟用網域探索）的詳細資訊，請參閱 Operations 檔中的 [管理您組織的 SIP 同盟提供者（Lync server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) ）。</span><span class="sxs-lookup"><span data-stu-id="cc960-112">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="cc960-113">如需使用 **CSAllowedDomain** Cmdlet 新增網域的詳細資訊，請參閱 Operations 檔中的 [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 。</span><span class="sxs-lookup"><span data-stu-id="cc960-113">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc960-114">Lync Online 客戶可以有多個網域。</span><span class="sxs-lookup"><span data-stu-id="cc960-114">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="cc960-115">如果您想要與一個以上的網域同盟，您必須為想要支援同盟的各個個別網域設定支援，並且 Lync Online 客戶的系統管理員必須啟用每個網域的同盟。</span><span class="sxs-lookup"><span data-stu-id="cc960-115">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="cc960-116">針對您要與其同盟的 Lync Online 2010 客戶網域，設定支援的主機提供者。</span><span class="sxs-lookup"><span data-stu-id="cc960-116">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="cc960-117">請使用本節中的程序，為裝載提供者設定相關支援。</span><span class="sxs-lookup"><span data-stu-id="cc960-117">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc960-118">此步驟僅適用于與 Lync Online 客戶網域的同盟，而不是用於同盟協力廠商所在位置之任何部署于內部部署的網域的同盟。</span><span class="sxs-lookup"><span data-stu-id="cc960-118">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="cc960-119">針對裝載提供者設定支援</span><span class="sxs-lookup"><span data-stu-id="cc960-119">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="cc960-120">在前端伺服器上，啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="cc960-120">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cc960-121">執行 **New-CsHostingProvider** Cmdlet，以建立和設定裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="cc960-121">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="cc960-122">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="cc960-122">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="cc960-123">上述範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="cc960-123">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="cc960-p105">**Identity** 會為您建立的裝載提供者指定唯一字串值識別碼。請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。</span><span class="sxs-lookup"><span data-stu-id="cc960-p105">**Identity** specifies a unique string value identifier for the hosting provider that you are creating. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="cc960-p106">**ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。您無法修改此值。如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。</span><span class="sxs-lookup"><span data-stu-id="cc960-p106">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="cc960-129">**VerificationLevel** 會指定如何驗證 (或是否驗證) 從裝載提供者傳送的訊息，以確認它們確實是傳送自該提供者。</span><span class="sxs-lookup"><span data-stu-id="cc960-129">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="cc960-p107">**Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True**，才能在兩個組織之間交換訊息。</span><span class="sxs-lookup"><span data-stu-id="cc960-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="cc960-132">**EnabledSharedAddressSpace** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。</span><span class="sxs-lookup"><span data-stu-id="cc960-132">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="cc960-133">**HostsOCSUsers** 會指出裝載提供者是否是用來裝載 Lync Server 帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc960-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="cc960-134">若 **為 False**，則提供者會主控其他帳戶類型，例如 Microsoft Exchange 帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc960-134">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="cc960-135">**IsLocal** 指出主控提供者所使用的 proxy 伺服器是否包含在 Lync server 拓撲中。</span><span class="sxs-lookup"><span data-stu-id="cc960-135">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="cc960-136">如需使用此 Cmdlet 的詳細資訊，請參閱 Operations 檔中的 [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 。</span><span class="sxs-lookup"><span data-stu-id="cc960-136">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

