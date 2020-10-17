---
title: 存取 Lync Server 公用 IM 連線布建網站
description: 存取 Lync Server 公用 IM 連線布建網站。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12916b12de1ef3a3f990c6bee54c312ba6c1992
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571129"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="da526-103">從 Lync Server 2013 存取 Lync Server 公用 IM 連線布建網站</span><span class="sxs-lookup"><span data-stu-id="da526-103">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da526-104">_**主題上次修改日期：** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="da526-104">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="da526-105">Lync-Skype 連線的布建處理已變更，與舊版的 PIC 布建方法相較。</span><span class="sxs-lookup"><span data-stu-id="da526-105">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="da526-106">此布建程式最多可能需要30天才能完成。</span><span class="sxs-lookup"><span data-stu-id="da526-106">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="da526-107">建議您先開始此程式，然後再完成本檔中的其餘步驟。</span><span class="sxs-lookup"><span data-stu-id="da526-107">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="da526-108">在您的帳戶中完成 Lync-Skype 布建程式之後，會啟用該帳戶，並為您的合格使用者啟用公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="da526-108">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="da526-109">若要布建 Lync-Skype 連線性，您需要下列資訊：</span><span class="sxs-lookup"><span data-stu-id="da526-109">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="da526-110">Microsoft 合約號碼</span><span class="sxs-lookup"><span data-stu-id="da526-110">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="da526-111">Access Edge service 完全限定功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="da526-111">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="da526-112">會話初始通訊協定 (SIP) 網域 (s) </span><span class="sxs-lookup"><span data-stu-id="da526-112">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="da526-113">任何其他的 Access Edge service Fqdn</span><span class="sxs-lookup"><span data-stu-id="da526-113">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="da526-114">連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="da526-114">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="da526-115">從2019年4月開始，我們將停止透過 pic.lync.com 網站為 Skype 同盟布建之客戶的連絡人資訊的收集和保留。</span><span class="sxs-lookup"><span data-stu-id="da526-115">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="da526-116">進行此變更是為了確保 pic.lync.com 布建系統遵守 Microsoft 隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="da526-116">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="da526-117">這種變更生效後，我們將無法再在暫止的布建變更上提供電子郵件更新。</span><span class="sxs-lookup"><span data-stu-id="da526-117">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="da526-118">PIC 布建變更通常會在進入之後的24-48 小時內完成。</span><span class="sxs-lookup"><span data-stu-id="da526-118">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="da526-119">如果您在提交布建要求之後仍會出現48小時的 Skype 同盟問題，請與 Microsoft 技術支援人員接洽，以進一步調查。</span><span class="sxs-lookup"><span data-stu-id="da526-119">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da526-120">做為此變更的一部分，所有先前輸入的連絡人資訊都會在2019年4月結束時從系統中清除。</span><span class="sxs-lookup"><span data-stu-id="da526-120">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="da526-121">若要啟動 Lync-Skype 連線的布建過程：</span><span class="sxs-lookup"><span data-stu-id="da526-121">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="da526-122"><strong>https://pic.lync.com</strong>使用您的 Microsoft Windows LIVE ID 登入網站。</span><span class="sxs-lookup"><span data-stu-id="da526-122">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="da526-123">選取 [Microsoft 授權合約] 類型。</span><span class="sxs-lookup"><span data-stu-id="da526-123">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="da526-124">選取 [確認您已讀取並接受 Lync 伺服器的產品使用權力] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="da526-124">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="da526-125">在 [ <strong>啟動</strong> 布建要求] 頁面上，按一下適當的連結，以啟動布建要求：</span><span class="sxs-lookup"><span data-stu-id="da526-125">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="da526-126">在 [ <strong>指定供給資訊</strong> ] 頁面上，輸入 <strong>ACCESS Edge service FQDN</strong>。</span><span class="sxs-lookup"><span data-stu-id="da526-126">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="da526-127">例如， <strong>sip.contoso.com</strong>。</span><span class="sxs-lookup"><span data-stu-id="da526-127">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="da526-128">2017年7月1日之後，Microsoft 將會另外要求客戶已部署用於公用 IM 連線的同盟 DNS SRV 記錄，以繼續運作。</span><span class="sxs-lookup"><span data-stu-id="da526-128">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="da526-129">輸入至少一或多個 SIP 功能變數名稱，然後按一下 [ <strong>新增</strong>]。</span><span class="sxs-lookup"><span data-stu-id="da526-129">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="da526-130">必須至少有一個 Access Edge server 與一個 SIP 網域，才可完成布建程式。</span><span class="sxs-lookup"><span data-stu-id="da526-130">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="da526-131">SIP 網域和 Access Edge server 在網路上必須是作用中、運作且可連線。</span><span class="sxs-lookup"><span data-stu-id="da526-131">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="da526-132">在 <strong>公用 IM 服務提供者</strong>的清單中，選取 [ <strong>Skype]，</strong> 然後按一下 <strong>[下一步]</strong> ，新增連絡人資訊，並提交布建要求。</span><span class="sxs-lookup"><span data-stu-id="da526-132">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="da526-133">在提交布建要求之後，最多可能需要30天的時間才能啟用該帳戶，且啟用使用者來進行公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="da526-133">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="da526-134">啟用同盟和公用 IM 連線 (PIC) </span><span class="sxs-lookup"><span data-stu-id="da526-134">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="da526-135">在您提交布建要求之後，您可以將重點放在 Lync Server 環境和設定 Lync-Skype 連線所需的管理工作上。</span><span class="sxs-lookup"><span data-stu-id="da526-135">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="da526-136">在本節中，我們假設 Lync Server 系統管理員已部署 Lync Server 和設定的外部存取。</span><span class="sxs-lookup"><span data-stu-id="da526-136">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="da526-137">如需設定 Lync Server 的外部存取的詳細資訊，請參閱的「規劃外部使用者存取」 [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) 和「部署外部使用者存取」 [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) 。</span><span class="sxs-lookup"><span data-stu-id="da526-137">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="da526-138">若要準備 Lync Server 環境以進行 Lync-Skype 連線，Lync Server 系統管理員必須完成下列三項任務：</span><span class="sxs-lookup"><span data-stu-id="da526-138">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="da526-139">1\.</span><span class="sxs-lookup"><span data-stu-id="da526-139">1\.</span></span> <span data-ttu-id="da526-140">設定同盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="da526-140">Configure Federation and PIC</span></span>

<span data-ttu-id="da526-141">需要同盟才能讓 Skype 使用者能夠與您組織中的 Lync 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="da526-141">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="da526-142">公用立即訊息連線 (PIC) 是同盟的類別，必須設定為讓 Lync 使用者能夠與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="da526-142">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="da526-143">同盟和 PIC 是使用 Lync Server 控制台進行設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="da526-143">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="da526-144">Live Communication Server 2005 SP1 或 Office 通訊伺服器2007不再支援 PIC 同盟。</span><span class="sxs-lookup"><span data-stu-id="da526-144">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="da526-145">支援的 PIC 同盟平臺包括 Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="da526-145">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="da526-146">2\.</span><span class="sxs-lookup"><span data-stu-id="da526-146">2\.</span></span> <span data-ttu-id="da526-147">設定至少一個原則以支援同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="da526-147">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="da526-148">使用 Lync Server 控制台，管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可以與內部 Lync Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="da526-148">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="da526-149">3\.</span><span class="sxs-lookup"><span data-stu-id="da526-149">3\.</span></span> <span data-ttu-id="da526-150">設定 Lync 的 Skype PIC 提供者設定</span><span class="sxs-lookup"><span data-stu-id="da526-150">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="da526-151">使用 Lync Server 管理命令介面，管理員必須設定 Lync 用戶端原則，以將 Skype 顯示為其他 PIC 提供者。</span><span class="sxs-lookup"><span data-stu-id="da526-151">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="da526-152"> (PIC) 服務提供者的公用立即訊息連線使用者無法參與您組織中的 IM 或會議，除非您在此程式之前設定至少一個原則 (步驟2，) 以支援公用 IM 連線能力。</span><span class="sxs-lookup"><span data-stu-id="da526-152">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="da526-153">若要設定同盟和 PIC，請參閱 at 中的「啟用或停用同盟和公用 IM 連線」 <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> 。</span><span class="sxs-lookup"><span data-stu-id="da526-153">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="da526-154">若要設定至少一個原則以支援同盟使用者存取，請參閱的「設定控制公用使用者存取的原則」 <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> 。</span><span class="sxs-lookup"><span data-stu-id="da526-154">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="da526-155">在 Lync Server 前端伺服器上，開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="da526-155">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="da526-156">執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="da526-156">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="da526-157">如果您的環境中還沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行 <STRONG>CsPublicProvider</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da526-157">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="da526-158">已新增于 Office 2013 中的 lync Server 2013 CU5 &amp; lync 桌面用戶端 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善了 Lync 使用者新增所需的 skype 連絡人，以識別並路由傳送至 skype (： user (contoso.com) @msn .com) 的情況。</span><span class="sxs-lookup"><span data-stu-id="da526-158">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="da526-159">在 [新增 Skype 連絡人] 對話方塊中，這些新設定將允許自動設定位址使用者輸入的格式，NameDecorationRoutingDomain (應設定為 msn.com) 如果不包含 NameDecorationExcludedDomainList 中的網域 (我們目前可支援 msn.com、live.com、Hotmail.com、outlook.com) 。</span><span class="sxs-lookup"><span data-stu-id="da526-159">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="da526-160">在 Lync 用戶端中，您現在可以選取 [Skype] 作為 PIC 提供者，並透過指定其 Microsoft 帳戶來新增 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="da526-160">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="da526-161">此外，已使用其 Microsoft 帳戶進行合併和登入的 Skype 使用者，可將連絡人要求傳送給 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="da526-161">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="da526-162">如需 Microsoft 帳戶的詳細資訊，請參閱 [什麼是 microsoft 帳戶？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。</span><span class="sxs-lookup"><span data-stu-id="da526-162">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="da526-163">如需將用戶端新增至 Lync 的詳細資訊，請參閱 [在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。</span><span class="sxs-lookup"><span data-stu-id="da526-163">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="da526-164">如需修改主控提供者的詳細資訊，請參閱 at 中的「建立或編輯主控的 SIP 同盟提供者」 [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) 。</span><span class="sxs-lookup"><span data-stu-id="da526-164">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="da526-165">這會完成必須在伺服器上執行的管理工作。</span><span class="sxs-lookup"><span data-stu-id="da526-165">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="da526-166">您現在已設定 Lync-Skype 連線能力。</span><span class="sxs-lookup"><span data-stu-id="da526-166">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="da526-167">其他資源</span><span class="sxs-lookup"><span data-stu-id="da526-167">Additional Resources</span></span>

[<span data-ttu-id="da526-168">在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者</span><span class="sxs-lookup"><span data-stu-id="da526-168">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="da526-169">Lync Server 2013 中的 Lync-Skype 連線布配指南</span><span class="sxs-lookup"><span data-stu-id="da526-169">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

