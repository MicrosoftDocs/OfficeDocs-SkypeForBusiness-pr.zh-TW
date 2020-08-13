---
title: Lync Server 2013：啟用 Lync-Skype 連線能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9cac7c88b2c3d9d6bd356a5340a5d4bb746e65a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="2997d-102">在 Lync Server 2013 中啟用 Lync-Skype 連線能力</span><span class="sxs-lookup"><span data-stu-id="2997d-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2997d-103">_**主題上次修改日期：** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="2997d-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="2997d-104">在您提交布建要求之後，您可以將重點放在 Lync Server 環境和設定 Lync-Skype 連線所需的管理工作上。</span><span class="sxs-lookup"><span data-stu-id="2997d-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="2997d-105">在本節中，我們假設 Lync Server 系統管理員已部署 Lync Server 和設定的外部存取。</span><span class="sxs-lookup"><span data-stu-id="2997d-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="2997d-106">如需設定 Lync Server 外部存取的詳細資訊，請參閱在 lync Server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md) 和 [部署 lync server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="2997d-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="2997d-107">若要準備 Lync Server 環境以進行 Lync-Skype 連線，Lync Server 系統管理員必須完成下列三項任務：</span><span class="sxs-lookup"><span data-stu-id="2997d-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="2997d-108">1\.</span><span class="sxs-lookup"><span data-stu-id="2997d-108">1\.</span></span> <span data-ttu-id="2997d-109">設定同盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="2997d-109">Configure Federation and PIC</span></span>

<span data-ttu-id="2997d-110">需要同盟才能讓 Skype 使用者能夠與您組織中的 Lync 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="2997d-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="2997d-111">公用立即訊息連線 (PIC) 是同盟的類別，必須設定為讓 Lync 使用者能夠與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="2997d-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="2997d-112">同盟和 PIC 是使用 Lync Server 控制台進行設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="2997d-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="2997d-113">![顯示 PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "顯示 PIC")</span><span class="sxs-lookup"><span data-stu-id="2997d-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2997d-114">Live Communication Server 2005 SP1 或 Office 通訊伺服器2007不再支援 PIC 同盟。</span><span class="sxs-lookup"><span data-stu-id="2997d-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="2997d-115">支援的 PIC 同盟平臺包括 Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="2997d-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="2997d-116">2\.</span><span class="sxs-lookup"><span data-stu-id="2997d-116">2\.</span></span> <span data-ttu-id="2997d-117">設定至少一個原則以支援同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="2997d-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="2997d-118">使用 Lync Server 控制台，管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可以與內部 Lync Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="2997d-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="2997d-119">![原則](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "原則")</span><span class="sxs-lookup"><span data-stu-id="2997d-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="2997d-120">3\.</span><span class="sxs-lookup"><span data-stu-id="2997d-120">3\.</span></span> <span data-ttu-id="2997d-121">設定 Lync 的 Skype PIC 提供者設定</span><span class="sxs-lookup"><span data-stu-id="2997d-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="2997d-122">使用 Lync Server 管理命令介面，管理員必須設定 Lync 用戶端原則，以將 Skype 顯示為其他 PIC 提供者。</span><span class="sxs-lookup"><span data-stu-id="2997d-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2997d-123"> (PIC) 服務提供者的公用立即訊息連線使用者無法參與您組織中的 IM 或音訊或視訊會議，除非您也在此程式中之前設定至少一個原則 (步驟2，) 以支援公用 IM 連線能力。</span><span class="sxs-lookup"><span data-stu-id="2997d-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="2997d-124">若要設定同盟和 PIC，請參閱 at 中的「啟用或停用同盟和公用 IM 連線」 [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) 。</span><span class="sxs-lookup"><span data-stu-id="2997d-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="2997d-125">若要設定至少一個原則以支援同盟使用者存取，請參閱的「設定控制公用使用者存取的原則」 [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) 。</span><span class="sxs-lookup"><span data-stu-id="2997d-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="2997d-126">**編輯現有的信使或 Skype PIC 提供者，並針對 Skype 進行設定**</span><span class="sxs-lookup"><span data-stu-id="2997d-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="2997d-127">在 Lync Server 前端伺服器上，開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="2997d-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="2997d-128">執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="2997d-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2997d-129">如果您的環境中還沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行 <STRONG>CsPublicProvider</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2997d-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2997d-130">已新增于 Office 2013 中的 lync Server 2013 CU5 &amp; lync 桌面用戶端 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善了 Lync 使用者新增所需的 skype 連絡人，以識別並路由傳送至 skype (： user (contoso.com) @msn .com) 的情況。</span><span class="sxs-lookup"><span data-stu-id="2997d-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="2997d-131">在 [新增 Skype 連絡人] 對話方塊中，這些新設定將允許自動設定位址使用者輸入的格式，NameDecorationRoutingDomain (應設定為 msn.com) 如果不包含 NameDecorationExcludedDomainList 中的網域 (我們目前可支援 msn.com、live.com、Hotmail.com、outlook.com) 。</span><span class="sxs-lookup"><span data-stu-id="2997d-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="2997d-132">在 Lync 用戶端中，您現在可以選取 [Skype] 作為 PIC 提供者，並透過指定其 Microsoft 帳戶來新增 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="2997d-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="2997d-133">此外，已使用其 Microsoft 帳戶進行合併和登入的 Skype 使用者，可將連絡人要求傳送給 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="2997d-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="2997d-134">如需 Microsoft 帳戶的詳細資訊，請參閱 [什麼是 microsoft 帳戶？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。</span><span class="sxs-lookup"><span data-stu-id="2997d-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="2997d-135">如需將用戶端新增至 Lync 的詳細資訊，請參閱 [在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。</span><span class="sxs-lookup"><span data-stu-id="2997d-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="2997d-136">![新增 Skype 連絡人](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "新增 Skype 連絡人")</span><span class="sxs-lookup"><span data-stu-id="2997d-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="2997d-137">如需修改主控提供者的詳細資訊，請參閱 at 中的「建立或編輯主控的 SIP 同盟提供者」 [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) 。</span><span class="sxs-lookup"><span data-stu-id="2997d-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="2997d-138">這會完成必須在伺服器上執行的管理工作。</span><span class="sxs-lookup"><span data-stu-id="2997d-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="2997d-139">您現在已設定 Lync-Skype 連線能力。</span><span class="sxs-lookup"><span data-stu-id="2997d-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

