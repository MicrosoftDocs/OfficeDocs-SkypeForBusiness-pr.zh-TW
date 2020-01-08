---
title: 整合內部部署整合訊息的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="832a6-102">整合內部部署 Unified Messaging 和 Lync Server 2013 的部署程序</span><span class="sxs-lookup"><span data-stu-id="832a6-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="832a6-103">_**主題上次修改日期：** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="832a6-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="832a6-104">如果您想要將 Exchange 整合通訊（UM）與 Lync Server 2013 整合，您必須執行本主題中所述的工作。</span><span class="sxs-lookup"><span data-stu-id="832a6-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="832a6-105">此外，請務必參閱[整合內部部署整合訊息和 Lync Server 2013 指南](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)中所述的規劃與部署最佳做法。</span><span class="sxs-lookup"><span data-stu-id="832a6-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="832a6-106">本主題假設您已將 Lync Server 2013 與 collocated 中繼伺服器一起部署，且您已為 Lync Server 2013 啟用使用者，但不一定已執行所有部署和設定步驟來啟用企業語音，如在部署檔中的[Lync Server 2013 中部署企業語音中](lync-server-2013-deploying-enterprise-voice.md)所述。</span><span class="sxs-lookup"><span data-stu-id="832a6-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="832a6-107">整合通訊流程整合程式</span><span class="sxs-lookup"><span data-stu-id="832a6-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="832a6-108">請務必與貴組織的 Exchange 管理員共同作業，以確認您要執行的工作，以協助確保順利、成功的整合。</span><span class="sxs-lookup"><span data-stu-id="832a6-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="832a6-109">分</span><span class="sxs-lookup"><span data-stu-id="832a6-109">Phase</span></span></th>
<th><span data-ttu-id="832a6-110">步驟</span><span class="sxs-lookup"><span data-stu-id="832a6-110">Steps</span></span></th>
<th><span data-ttu-id="832a6-111">必要的群組和角色</span><span class="sxs-lookup"><span data-stu-id="832a6-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="832a6-112">部署檔</span><span class="sxs-lookup"><span data-stu-id="832a6-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="832a6-113">部署下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="832a6-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="832a6-114">Microsoft Exchange Server 2007 Service Pack 1 （SP2）或最新 Service pack</span><span class="sxs-lookup"><span data-stu-id="832a6-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="832a6-115">Microsoft Exchange Server 2010 或最新 service pack</span><span class="sxs-lookup"><span data-stu-id="832a6-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="832a6-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="832a6-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="832a6-117">如果您使用的是 Microsoft Exchange Server 2013，請在與 Lync Server 2013 相同的林中或不同的林中，安裝下列 Exchange Server 角色：</span><span class="sxs-lookup"><span data-stu-id="832a6-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="832a6-118">用戶端存取</span><span class="sxs-lookup"><span data-stu-id="832a6-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="832a6-119">控制</span><span class="sxs-lookup"><span data-stu-id="832a6-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="832a6-120">如果 Microsoft Exchange Server 2013 與 Exchange 整合通訊（UM）安裝在不同的林中，請將每個 Exchange 林設定為信任 Lync Server 2013 林。</span><span class="sxs-lookup"><span data-stu-id="832a6-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="832a6-121">如果您使用的是 Exchange 2010，請在與 Lync Server 2013 相同的林中或不同的林中，安裝下列 Exchange 伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="832a6-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="832a6-122">整合通訊</span><span class="sxs-lookup"><span data-stu-id="832a6-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="832a6-123">中樞傳輸</span><span class="sxs-lookup"><span data-stu-id="832a6-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="832a6-124">用戶端存取</span><span class="sxs-lookup"><span data-stu-id="832a6-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="832a6-125">控制</span><span class="sxs-lookup"><span data-stu-id="832a6-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="832a6-126">如果 Lync Server 2013 與 Exchange 整合通訊（UM）安裝在不同的林中，請將每個 Exchange 林設定為信任 Lync Server 2013 林。</span><span class="sxs-lookup"><span data-stu-id="832a6-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="832a6-127">企業系統管理員（如果這是組織中的第一個 Exchange 伺服器）</span><span class="sxs-lookup"><span data-stu-id="832a6-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="832a6-128">或</span><span class="sxs-lookup"><span data-stu-id="832a6-128">-OR-</span></span></p>
<p><span data-ttu-id="832a6-129">Exchange 組織管理員（如果這不是組織中的第一個 Exchange 伺服器）</span><span class="sxs-lookup"><span data-stu-id="832a6-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="832a6-130">請參閱適用于您 Exchange 伺服器版本的相關檔：</span><span class="sxs-lookup"><span data-stu-id="832a6-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="832a6-131">Exchange Server 2007 部署檔位於<a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>。</span><span class="sxs-lookup"><span data-stu-id="832a6-131">Exchange Server 2007 deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="832a6-132">Exchange Server 2010 或最新的 service pack 部署<a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>檔在。</span><span class="sxs-lookup"><span data-stu-id="832a6-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="832a6-133">Microsoft Exchange Server 2013 規劃和部署<a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>。</span><span class="sxs-lookup"><span data-stu-id="832a6-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="832a6-134">安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="832a6-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="832a6-135">從信任的根憑證授權單位（CA）下載並安裝每個 Exchange UM 伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="832a6-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="832a6-136">在執行 Exchange UM 和 Lync Server 2013 的伺服器之間，雙方傳輸層級安全性（MTLS）都需要有證書。</span><span class="sxs-lookup"><span data-stu-id="832a6-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="832a6-137">人員</span><span class="sxs-lookup"><span data-stu-id="832a6-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="832a6-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">在運行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證</a></span><span class="sxs-lookup"><span data-stu-id="832a6-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="832a6-139">建立及設定新的 Exchange UM SIP 撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="832a6-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="832a6-140">在 Exchange UM 伺服器上，根據貴組織的特定部署需求來建立 SIP 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="832a6-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="832a6-141">Exchange 組織管理員</span><span class="sxs-lookup"><span data-stu-id="832a6-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="832a6-142">若為 Exchange 2007 SP1 或最新的 service &quot;pack，請參閱如何在<a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>建立整合通訊 SIP&quot; URI 撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="832a6-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="832a6-143">若為 Exchange 2010 或最新的 service &quot;pack，請參閱在&quot;上<a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>建立 UM 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="832a6-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="832a6-144">若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</span><span class="sxs-lookup"><span data-stu-id="832a6-144">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="832a6-145">設定 Exchange UM SIP 撥號方案的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="832a6-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="832a6-146">若要加密企業語音流量，請將 Exchange UM SIP 撥號方案的安全性設定設定為 [ <strong>SIP 安全</strong>] 或 [<strong>安全</strong>的]。</span><span class="sxs-lookup"><span data-stu-id="832a6-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="832a6-147">如果您已在您的環境中部署或規劃部署 Lync Phone Edition 裝置，這是一個特別重要的步驟。</span><span class="sxs-lookup"><span data-stu-id="832a6-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="832a6-148">若要讓 Lync Phone Edition 裝置在使用 Exchange UM 整合的環境中運作，Lync Server 加密設定必須與 Exchange UM 撥號方案安全性設定一致。</span><span class="sxs-lookup"><span data-stu-id="832a6-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="832a6-149">如需詳細資訊，請參閱部署檔。</span><span class="sxs-lookup"><span data-stu-id="832a6-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="832a6-150">Exchange 組織管理員</span><span class="sxs-lookup"><span data-stu-id="832a6-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="832a6-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange for Lync Server 2013 中設定整合通訊</a></span><span class="sxs-lookup"><span data-stu-id="832a6-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="832a6-152">若是 Exchange 2007 SP1 或最新的 service pack，請參閱：</span><span class="sxs-lookup"><span data-stu-id="832a6-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="832a6-153">&quot;如何在&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>整合的郵件撥號方案上設定安全性。</span><span class="sxs-lookup"><span data-stu-id="832a6-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="832a6-154">若是 Exchange 2010 或最新的 service pack，請參閱：</span><span class="sxs-lookup"><span data-stu-id="832a6-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="832a6-155">&quot;在 UM 撥號方案&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>上設定 VoIP 安全性。</span><span class="sxs-lookup"><span data-stu-id="832a6-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="832a6-156">若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</span><span class="sxs-lookup"><span data-stu-id="832a6-156">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="832a6-157">將整合郵件伺服器新增至 Exchange UM SIP 撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="832a6-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="832a6-158">若要讓新安裝的整合通訊伺服器應答並處理來電，您必須將統一訊息伺服器新增到 UM 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="832a6-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="832a6-159">在這種情況下，請將伺服器新增到 Exchange UM SIP 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="832a6-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="832a6-160">人員</span><span class="sxs-lookup"><span data-stu-id="832a6-160">Administrators</span></span></p>
<p><span data-ttu-id="832a6-161">Exchange Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="832a6-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="832a6-162">針對 Exchange 2007 SP1 或最新的 service pack &quot;，請參閱如何將整合郵件伺服器新增至&quot;撥號<a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>計畫。</span><span class="sxs-lookup"><span data-stu-id="832a6-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="832a6-163">若為 Exchange 2010 或最新的 service &quot;pack，請參閱在上<a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>查看或設定&quot; UM 伺服器的屬性。</span><span class="sxs-lookup"><span data-stu-id="832a6-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="832a6-164">若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</span><span class="sxs-lookup"><span data-stu-id="832a6-164">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="832a6-165">使用 SIP 位址設定信箱。</span><span class="sxs-lookup"><span data-stu-id="832a6-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="832a6-166">將 SIP 位址指派給將使用 Exchange UM 功能之企業語音使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="832a6-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="832a6-167">Lync Server 2013 系統管理員</span><span class="sxs-lookup"><span data-stu-id="832a6-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="832a6-168">Exchange 收件者管理員</span><span class="sxs-lookup"><span data-stu-id="832a6-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="832a6-169">若為 Exchange 2007 SP1 或最新的 service &quot;pack，請參閱如何在上&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>新增、移除或修改啟用 UM 的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="832a6-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="832a6-170">若為 Exchange 2010 或最新的 service &quot;pack，請參閱在上<a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>修改啟用 UM 的&quot;使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="832a6-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="832a6-171">若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</span><span class="sxs-lookup"><span data-stu-id="832a6-171">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="832a6-172">執行 exchucutil. ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="832a6-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="832a6-173">在執行 Exchange UM 服務的伺服器上，開啟 Exchange 管理命令介面，並執行 exchucutil. ps1 腳本，此腳本會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="832a6-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="832a6-174">授予 Lync Server 2013 讀取 Exchange UM Active Directory 網域服務物件的許可權，特別是在前一個工作中建立的 SIP 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="832a6-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="832a6-175">在 Active Directory 中針對每一個 Lync Server 2013 企業版文件庫或標準版伺服器（宿主已啟用企業語音的使用者）建立統一通訊 IP 閘道物件。</span><span class="sxs-lookup"><span data-stu-id="832a6-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="832a6-176">針對每個閘道建立 Exchange UM 查尋群組。</span><span class="sxs-lookup"><span data-stu-id="832a6-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="832a6-177">[查尋] 群組試點識別碼將是與對應的閘道相關聯的撥號方案名稱。</span><span class="sxs-lookup"><span data-stu-id="832a6-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="832a6-178">如果有一個以上的撥號方案，則需要將這些專案對應至1:1。</span><span class="sxs-lookup"><span data-stu-id="832a6-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="832a6-179">Exchange 組織管理員</span><span class="sxs-lookup"><span data-stu-id="832a6-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="832a6-180">Exchange 收件者管理員</span><span class="sxs-lookup"><span data-stu-id="832a6-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="832a6-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange for Lync Server 2013 中設定整合通訊</a></span><span class="sxs-lookup"><span data-stu-id="832a6-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="832a6-182">設定 Lync Server 2013 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="832a6-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="832a6-183">如果您要與 Exchange 2007 SP1 或最新的 service pack （或 Exchange 2010）整合，請建立新的企業語音撥號方案，其名稱必須符合 Exchange UM 撥號方案的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="832a6-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="832a6-184">您將需要針對每個 UM 撥號方案進行這項作業。</span><span class="sxs-lookup"><span data-stu-id="832a6-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="832a6-185">如果您要與 Exchange 2010 SP1 整合，請確定已設定適當的全域/網站層級或池層級的企業語音撥號方案。</span><span class="sxs-lookup"><span data-stu-id="832a6-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="832a6-186">如果您要與 Exchange 2010 SP1 整合，Lync Server 撥號方案與 Exchange UM SIP 撥號方案名稱不需相符。</span><span class="sxs-lookup"><span data-stu-id="832a6-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="832a6-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="832a6-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="832a6-188"><a href="lync-server-2013-configuring-dial-plans.md">在 Lync Server 2013 中設定撥號對應表</a></span><span class="sxs-lookup"><span data-stu-id="832a6-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="832a6-189">執行 Exchange UM 整合工具。</span><span class="sxs-lookup"><span data-stu-id="832a6-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="832a6-190">在 Lync Server 2013 上，執行<strong>ocsumutil</strong>，這是：</span><span class="sxs-lookup"><span data-stu-id="832a6-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="832a6-191">建立訂閱者存取權及自動語音應答連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="832a6-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="832a6-192">驗證是否有符合 Exchange UM 撥號方案 FQDN 之名稱的企業語音撥號方案。</span><span class="sxs-lookup"><span data-stu-id="832a6-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="832a6-193">如果您執行的是 Exchange 2010 SP1 或更新版本，撥號方案名稱不需要符合，而且您可以略過工具對此所做的警告。</span><span class="sxs-lookup"><span data-stu-id="832a6-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="832a6-194">此工具的運作方式是掃描 Exchange UM 設定的 Active Directory，並允許 Lync Server 2013 系統管理員來查看、建立及編輯連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="832a6-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="832a6-195">RTCUniversalServerAdmins<em>和</em>RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="832a6-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="832a6-196">若要成功執行 ocsumutil，使用者必須屬於這兩個群組。</span><span class="sxs-lookup"><span data-stu-id="832a6-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="832a6-197">若要建立連絡人物件，執行 ocsumutil 的使用者必須擁有儲存新連絡人物件之 Active Directory 組織單位（OU）的正確許可權。</span><span class="sxs-lookup"><span data-stu-id="832a6-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="832a6-198">您可以執行<STRONG>授與 CsOUPermission</STRONG> Cmdlet 來授與此許可權。</span><span class="sxs-lookup"><span data-stu-id="832a6-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="832a6-199">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="832a6-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="832a6-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">設定 Lync Server 2013 以搭配 Microsoft Exchange Server 上的 Unified Messaging 使用</a></span><span class="sxs-lookup"><span data-stu-id="832a6-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="832a6-201">如有需要，請執行其他企業語音設定步驟。</span><span class="sxs-lookup"><span data-stu-id="832a6-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="832a6-202">如果您尚未在伺服器或使用者上設定 [企業語音設定]，請執行下列其中一項或多項操作：</span><span class="sxs-lookup"><span data-stu-id="832a6-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="832a6-203">部署和設定</span><span class="sxs-lookup"><span data-stu-id="832a6-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="832a6-204">公用交換式電話網絡（PSTN）閘道和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="832a6-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="832a6-205">定義語音原則、PSTN 使用方式記錄，以及傳出通話路由。</span><span class="sxs-lookup"><span data-stu-id="832a6-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="832a6-206">允許使用者使用企業語音。</span><span class="sxs-lookup"><span data-stu-id="832a6-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="832a6-207">您也可以選擇使用撥號方案設定特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="832a6-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="832a6-208">根據您所啟用的企業語音功能，可能需要其他配置步驟。</span><span class="sxs-lookup"><span data-stu-id="832a6-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="832a6-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="832a6-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="832a6-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="832a6-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="832a6-211">請參閱下列各節中的主題：</span><span class="sxs-lookup"><span data-stu-id="832a6-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="832a6-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由</a></span><span class="sxs-lookup"><span data-stu-id="832a6-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="832a6-213"><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企業版語音</a></span><span class="sxs-lookup"><span data-stu-id="832a6-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="832a6-214">針對 Exchange UM 啟用企業語音使用者。</span><span class="sxs-lookup"><span data-stu-id="832a6-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="832a6-215">在 Exchange UM 伺服器上，確定已建立統一訊息信箱原則，且每位使用者都有唯一的分機號碼指派，然後讓使用者使用統一訊息。</span><span class="sxs-lookup"><span data-stu-id="832a6-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="832a6-216">Exchange 收件者管理員</span><span class="sxs-lookup"><span data-stu-id="832a6-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="832a6-217">若為 Exchange 2007 SP1 或最新的 service &quot;pack，請參閱如何為使用者啟用&quot;整合<a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>訊息。</span><span class="sxs-lookup"><span data-stu-id="832a6-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="832a6-218">若為 Exchange 2010 或最新的 service &quot;pack，請參閱在<a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>下列&quot;啟用整合通訊的使用者。</span><span class="sxs-lookup"><span data-stu-id="832a6-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="832a6-219">若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</span><span class="sxs-lookup"><span data-stu-id="832a6-219">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

