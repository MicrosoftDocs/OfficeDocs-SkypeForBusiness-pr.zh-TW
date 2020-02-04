---
title: 存取 Lync Server 公用 IM 連線佈建網站
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
ms.openlocfilehash: dbcb2e46380e7ed4bbd8499e83f638cb314844e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="63674-102">透過 Lync Server 2013 存取 Lync Server 公用 IM 連線佈建網站</span><span class="sxs-lookup"><span data-stu-id="63674-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63674-103">_**主題上次修改日期：** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="63674-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="63674-104">Lync-Skype 連線的提供程式已變更，與先前的 PIC 自動設定方法相比。</span><span class="sxs-lookup"><span data-stu-id="63674-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="63674-105">此設定程式可能需要長達三十天才能完成。</span><span class="sxs-lookup"><span data-stu-id="63674-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="63674-106">我們建議您先開始這個程式，然後再完成這份檔中的其餘步驟。</span><span class="sxs-lookup"><span data-stu-id="63674-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="63674-107">針對您的帳戶完成 Lync Skype 預配程式後，該帳戶即會啟用，且您的合格使用者可供公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="63674-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="63674-108">若要設定 Lync-Skype 連線性，您需要下列資訊：</span><span class="sxs-lookup"><span data-stu-id="63674-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="63674-109">Microsoft 協定編號</span><span class="sxs-lookup"><span data-stu-id="63674-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="63674-110">Access Edge 服務的完整功能變數名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="63674-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="63674-111">會話初始通訊協定（SIP）網域</span><span class="sxs-lookup"><span data-stu-id="63674-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="63674-112">任何其他存取邊緣服務 Fqdn</span><span class="sxs-lookup"><span data-stu-id="63674-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="63674-113">連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="63674-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="63674-114">從2019年4月開始，我們會針對透過 pic.lync.com 網站提供 Skype Federation 的客戶停止收集及保留連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="63674-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="63674-115">我們正在進行這種變更，以確保 pic.lync.com 置備系統符合 Microsoft 隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="63674-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="63674-116">此變更生效之後，我們將無法在未決的置備變更上提供電子郵件更新。</span><span class="sxs-lookup"><span data-stu-id="63674-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="63674-117">PIC 置備變更通常會在輸入後的24-48 小時內完成。</span><span class="sxs-lookup"><span data-stu-id="63674-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="63674-118">如果您在提交提供要求之後，仍會遇到48小時的 Skype Federation 問題，請與 Microsoft 技術支援人員聯繫，以進一步調查。</span><span class="sxs-lookup"><span data-stu-id="63674-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63674-119">如此一來，在2019年4月結束後，所有先前輸入的連絡人資訊都會從我們的系統中清除。</span><span class="sxs-lookup"><span data-stu-id="63674-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="63674-120">若要啟動 Lync Skype 連線的置備程式：</span><span class="sxs-lookup"><span data-stu-id="63674-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="63674-121">使用您的 Microsoft Windows Live <strong>https://pic.lync.com</strong>ID 登入網站。</span><span class="sxs-lookup"><span data-stu-id="63674-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="63674-122">選取 Microsoft 授權合約類型。</span><span class="sxs-lookup"><span data-stu-id="63674-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="63674-123">選取核取方塊，確認您已閱讀並接受 Lync Server 的產品使用權力。</span><span class="sxs-lookup"><span data-stu-id="63674-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="63674-124">在 [<strong>啟動提供要求</strong>] 頁面上，按一下適當的連結以啟動提供要求：</span><span class="sxs-lookup"><span data-stu-id="63674-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="63674-125">在 [<strong>指定供給資訊</strong>] 頁面上，輸入<strong>存取邊緣服務 FQDN</strong>。</span><span class="sxs-lookup"><span data-stu-id="63674-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="63674-126">例如， <strong>sip.contoso.com</strong>。</span><span class="sxs-lookup"><span data-stu-id="63674-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="63674-127">2017年7月1日之後，Microsoft 會進一步要求客戶提供公用 IM 連線的同盟 DNS SRV 記錄來繼續運作。</span><span class="sxs-lookup"><span data-stu-id="63674-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="63674-128">輸入至少一個或多個 SIP 功能變數名稱，然後按一下 [<strong>新增</strong>]。</span><span class="sxs-lookup"><span data-stu-id="63674-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="63674-129">至少需要一個存取邊緣伺服器和一個 SIP 網域，才能完成置備程式。</span><span class="sxs-lookup"><span data-stu-id="63674-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="63674-130">SIP 網域和存取邊緣伺服器在網路上必須是作用中、正常運作且可存取的。</span><span class="sxs-lookup"><span data-stu-id="63674-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="63674-131">在<strong>公用 IM 服務提供者</strong>清單中，選取 [ <strong>Skype]，</strong>然後按一下<strong>[下一步]</strong>以新增連絡人資訊，並提交置備要求。</span><span class="sxs-lookup"><span data-stu-id="63674-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="63674-132">在提交預配要求之後，最多可能需要30天的時間，才能啟動該帳戶，以及啟用公用 IM 連線的使用者。</span><span class="sxs-lookup"><span data-stu-id="63674-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="63674-133">啟用同盟與公用 IM 連線（PIC）</span><span class="sxs-lookup"><span data-stu-id="63674-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="63674-134">在您提交提供要求之後，您就可以將焦點放在 Lync Server 環境，以及設定 Lync Skype 連線所需的管理工作上。</span><span class="sxs-lookup"><span data-stu-id="63674-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="63674-135">在本節中，我們假設 Lync Server 系統管理員已部署 Lync Server 並設定外部存取。</span><span class="sxs-lookup"><span data-stu-id="63674-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="63674-136">如需有關設定 Lync Server 外部存取的其他資訊，請參閱「規劃外部使用者存取」 [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772)和「部署外部使用者存取」 [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)。</span><span class="sxs-lookup"><span data-stu-id="63674-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="63674-137">若要準備 lync Server 環境以進行 Lync 與 Skype 連線，Lync Server 管理員必須完成下列三項工作：</span><span class="sxs-lookup"><span data-stu-id="63674-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="63674-138">1。</span><span class="sxs-lookup"><span data-stu-id="63674-138">1\.</span></span> <span data-ttu-id="63674-139">設定同盟與 PIC</span><span class="sxs-lookup"><span data-stu-id="63674-139">Configure Federation and PIC</span></span>

<span data-ttu-id="63674-140">必須具備同盟，才能讓 Skype 使用者與您組織中的 Lync 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="63674-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="63674-141">公用立即訊息連線（PIC）是一種同盟類別，而且必須加以設定，才能讓 Lync 使用者與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="63674-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="63674-142">[同盟] 和 [PIC] 是使用 Lync Server [控制台] 進行設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="63674-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="63674-143">即時通訊伺服器 2005 SP1 或 Office 通訊伺服器2007不再支援 PIC 同盟。</span><span class="sxs-lookup"><span data-stu-id="63674-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="63674-144">適用于 PIC 同盟的支援平臺包括 Lync Server 2013、Lync Server 2010 及 Office 通訊伺服器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="63674-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="63674-145">2。</span><span class="sxs-lookup"><span data-stu-id="63674-145">2\.</span></span> <span data-ttu-id="63674-146">至少設定一個要支援同盟使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="63674-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="63674-147">在 Lync Server [控制台] 中，系統管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可與內部 Lync 伺服器使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="63674-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="63674-148">3。</span><span class="sxs-lookup"><span data-stu-id="63674-148">3\.</span></span> <span data-ttu-id="63674-149">設定 Lync 的 Skype PIC 提供者設定</span><span class="sxs-lookup"><span data-stu-id="63674-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="63674-150">如果您使用 Lync Server 管理命令介面，系統管理員必須設定 Lync 用戶端原則，將 Skype 顯示為額外的 PIC 提供者。</span><span class="sxs-lookup"><span data-stu-id="63674-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="63674-151">公用立即訊息連線（PIC）服務提供者的使用者無法在您的組織中參與 IM 或會議，除非您在此程式中設定至少一個原則（步驟2），才能支援公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="63674-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="63674-152">若要設定同盟和 PIC，請參閱「啟用或停用同盟與公用 IM <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>連線」。</span><span class="sxs-lookup"><span data-stu-id="63674-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="63674-153">若要至少設定一個支援同盟使用者存取的原則，請參閱「設定控制公用使用者存取的原則」 <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>。</span><span class="sxs-lookup"><span data-stu-id="63674-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="63674-154">從 Lync Server 前端伺服器開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="63674-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="63674-155">執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="63674-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="63674-156">如果您的環境中還沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行<STRONG>CsPublicProvider</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="63674-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="63674-157">在 Lync Server 2013 中新增&amp; OFFICE 2013 SP1 中的 CU5 lync 桌面用戶端，這會改善 lync 使用者新增必要的 skype 連絡人至「保密協定」，以找出並將其路由至 Skype （格式為：使用者（contoso .com） @msn .com）。</span><span class="sxs-lookup"><span data-stu-id="63674-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="63674-158">這些新設定可讓您在 [新增 Skype 連絡人] 對話方塊中的 [新增 Skype 連絡人] 對話方塊中，自動設定位址格式，但如果它不包含 NameDecorationExcludedDomainList 中的網域，則為 NameDecorationRoutingDomain （應設定為 msn.com）。我們目前可以支援 msn.com、live.com、Hotmail.com、outlook.com）。</span><span class="sxs-lookup"><span data-stu-id="63674-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="63674-159">您現在可以從 Lync 用戶端選取 [Skype] 作為 PIC 提供者，並透過指定其 Microsoft 帳戶來新增 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="63674-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="63674-160">此外，已透過其 Microsoft 帳戶合併並登入的 Skype 使用者，可以傳送聯絡人要求給 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="63674-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="63674-161">如需 Microsoft 帳戶的詳細資訊，請參閱[什麼是 microsoft 帳戶？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。</span><span class="sxs-lookup"><span data-stu-id="63674-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="63674-162">如需將用戶端新增至 Lync 的其他資訊，請參閱[在 Lync Server 2013 中使用 Lync Skype 連線功能做為最終使用者](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。</span><span class="sxs-lookup"><span data-stu-id="63674-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="63674-163">如需有關修改託管提供者的詳細資訊，請參閱「建立或編輯託管 SIP [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)聯盟提供者」。</span><span class="sxs-lookup"><span data-stu-id="63674-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="63674-164">這樣就完成了必須在伺服器上執行的系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="63674-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="63674-165">您現在已設定 Lync-Skype 連線的連線。</span><span class="sxs-lookup"><span data-stu-id="63674-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="63674-166">其他資源</span><span class="sxs-lookup"><span data-stu-id="63674-166">Additional Resources</span></span>

[<span data-ttu-id="63674-167">在 Lync Server 2013 中以使用者身分使用 Lync-Skype 連線</span><span class="sxs-lookup"><span data-stu-id="63674-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="63674-168">Lync Server 2013 的 Lync-Skype 連線佈建指南</span><span class="sxs-lookup"><span data-stu-id="63674-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

