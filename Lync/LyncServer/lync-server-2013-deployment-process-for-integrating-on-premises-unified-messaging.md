---
title: 整合內部部署整合通訊的部署程式
description: 整合內部部署整合通訊的部署程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1b8f528edb970893198ed06b821535a398f09d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569519"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="2afdb-103">整合內部部署整合通訊和 Lync Server 2013 的部署程式</span><span class="sxs-lookup"><span data-stu-id="2afdb-103">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2afdb-104">_**主題上次修改日期：** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="2afdb-104">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="2afdb-105">如果您想要整合 Exchange 整合通訊 (UM) 與 Lync Server 2013，您必須執行本主題中所述的工作。</span><span class="sxs-lookup"><span data-stu-id="2afdb-105">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="2afdb-106">此外，請務必查看 [有關整合內部部署整合通訊和 Lync Server 2013 的指導方針](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)中所述的規劃及部署最佳作法。</span><span class="sxs-lookup"><span data-stu-id="2afdb-106">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="2afdb-107">本主題假設您已部署 Lync Server 2013 與組合轉送伺服器，且已針對 Lync Server 2013 啟用使用者，但不一定已執行所有部署和設定步驟來啟用企業語音，如部署檔中的 [Lync Server 2013 中的部署企業語音](lync-server-2013-deploying-enterprise-voice.md) 所述。</span><span class="sxs-lookup"><span data-stu-id="2afdb-107">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="2afdb-108">Unified Messaging 整合程序</span><span class="sxs-lookup"><span data-stu-id="2afdb-108">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2afdb-109">請務必與組織的 Exchange 系統管理員協調，以確認您將執行的各項工作，以協助確保順利、成功的整合。</span><span class="sxs-lookup"><span data-stu-id="2afdb-109">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="2afdb-110">階段</span><span class="sxs-lookup"><span data-stu-id="2afdb-110">Phase</span></span></th>
<th><span data-ttu-id="2afdb-111">步驟</span><span class="sxs-lookup"><span data-stu-id="2afdb-111">Steps</span></span></th>
<th><span data-ttu-id="2afdb-112">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="2afdb-112">Required groups and roles</span></span></th>
<th><span data-ttu-id="2afdb-113">部署文件</span><span class="sxs-lookup"><span data-stu-id="2afdb-113">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2afdb-114">部署下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="2afdb-114">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2afdb-115">Microsoft Exchange Server 2007 Service Pack 1 (SP2) 或最新的 service pack</span><span class="sxs-lookup"><span data-stu-id="2afdb-115">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="2afdb-116">Microsoft Exchange Server 2010 或最新的 service pack</span><span class="sxs-lookup"><span data-stu-id="2afdb-116">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="2afdb-117">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="2afdb-117">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2afdb-118">如果您使用的是 Microsoft Exchange Server 2013，請在相同樹系或不同的樹系中，將下列 Exchange Server 角色安裝為 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="2afdb-118">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="2afdb-119">Client Access</span><span class="sxs-lookup"><span data-stu-id="2afdb-119">Client Access</span></span></p></li>
<li><p><span data-ttu-id="2afdb-120">信箱</span><span class="sxs-lookup"><span data-stu-id="2afdb-120">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="2afdb-121">如果 Microsoft Exchange Server 2013 和 Exchange 整合通訊 (UM) 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任 Lync Server 2013 樹系。</span><span class="sxs-lookup"><span data-stu-id="2afdb-121">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="2afdb-122">如果您使用的是 Exchange 2010，請在相同樹系或不同樹系中，將下列 Exchange 伺服器角色安裝為 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="2afdb-122">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="2afdb-123">Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="2afdb-123">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="2afdb-124">Hub Transport</span><span class="sxs-lookup"><span data-stu-id="2afdb-124">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="2afdb-125">Client Access</span><span class="sxs-lookup"><span data-stu-id="2afdb-125">Client Access</span></span></p></li>
<li><p><span data-ttu-id="2afdb-126">信箱</span><span class="sxs-lookup"><span data-stu-id="2afdb-126">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="2afdb-127">如果 Lync Server 2013 和 Exchange 整合通訊 (UM) 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任 Lync Server 2013 樹系。</span><span class="sxs-lookup"><span data-stu-id="2afdb-127">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-128">企業的系統管理員 (如果這是組織中的第一部 Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="2afdb-128">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="2afdb-129">-或-</span><span class="sxs-lookup"><span data-stu-id="2afdb-129">-OR-</span></span></p>
<p><span data-ttu-id="2afdb-130">Exchange 組織系統管理員 (如果這不是組織中的第一部 Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="2afdb-130">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="2afdb-131">請參閱您的 Exchange Server 版本所適用的文件：</span><span class="sxs-lookup"><span data-stu-id="2afdb-131">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2afdb-132">Exchange Server 2007 部署檔，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-132">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2afdb-133">Exchange Server 2010 或最新的 service pack 部署檔，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-133">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2afdb-134">Microsoft Exchange Server 2013 規劃和部署于 <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-134">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afdb-135">安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="2afdb-135">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-136">從受信任的憑證授權單位單位 (CA) 下載並安裝每個 Exchange UM 伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="2afdb-136">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="2afdb-137">在執行 Exchange UM 和 Lync Server 2013 的伺服器之間，相互傳輸層級安全性 (MTLS) 皆需要憑證。</span><span class="sxs-lookup"><span data-stu-id="2afdb-137">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-138">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-138">Administrators</span></span></p></td>
<td><p><span data-ttu-id="2afdb-139"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證</a></span><span class="sxs-lookup"><span data-stu-id="2afdb-139"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2afdb-140">建立並設定新的 Exchange UM SIP 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-140">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-141">在 Exchange UM 伺服器上，根據您組織的特定部署需求建立 SIP 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-141">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-142">Exchange 組織系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-142">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="2afdb-143">如需 Exchange 2007 SP1 或最新的 service pack，請參閱 how &quot; To Create a 整合通訊 SIP URI 撥號對應表的方式 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-143">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="2afdb-144">若為 Exchange 2010 或最新的 service pack，請參閱 &quot; Create a UM 撥號對應表 &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-144">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="2afdb-145">若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-145">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afdb-146">設定 Exchange UM SIP 撥號對應表的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="2afdb-146">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-147">若要加密 Enterprise Voice 流量，請將 Exchange UM SIP 撥號對應表上的安全性設定設定為 [ <strong>SIP 安全</strong> ] 或 [ <strong>安全</strong>]。</span><span class="sxs-lookup"><span data-stu-id="2afdb-147">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="2afdb-148">如果您已在環境中部署或規劃部署 Lync Phone Edition 裝置，則此為特別重要的步驟。</span><span class="sxs-lookup"><span data-stu-id="2afdb-148">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="2afdb-149">若要讓 Lync Phone Edition 裝置在具有 Exchange UM 整合的環境中運作，Lync Server 加密設定必須與 Exchange UM 撥號對應表安全性設定對齊。</span><span class="sxs-lookup"><span data-stu-id="2afdb-149">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="2afdb-150">如需詳細資訊，請參閱＜部署＞文件。</span><span class="sxs-lookup"><span data-stu-id="2afdb-150">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-151">Exchange 組織系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-151">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="2afdb-152"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 上設定 Lync Server 2013 的整合通訊</a></span><span class="sxs-lookup"><span data-stu-id="2afdb-152"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2afdb-153">針對 Exchange 2007 SP1 或最新的 service pack，另請參閱：</span><span class="sxs-lookup"><span data-stu-id="2afdb-153">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="2afdb-154">&quot;如何在整合通訊撥號對應表上設定安全性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-154">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="2afdb-155">對於 Exchange 2010 或最新的 Service Pack，另請參閱：</span><span class="sxs-lookup"><span data-stu-id="2afdb-155">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="2afdb-156">&quot;在 UM 撥號對應表上設定 VoIP 安全性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-156">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="2afdb-157">若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-157">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2afdb-158">將整合通訊伺服器新增至 Exchange UM SIP 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-158">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-159">若要讓新安裝的 Unified Messaging 伺服器能夠接聽及處理來電，您必須將 Unified Messaging 伺服器新增至 UM 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-159">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="2afdb-160">在此情況下，請將伺服器新增至 Exchange UM SIP 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-160">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-161">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-161">Administrators</span></span></p>
<p><span data-ttu-id="2afdb-162">Exchange Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-162">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="2afdb-163">若為 Exchange 2007 SP1 或最新的 service pack，請參閱 how &quot; To Add 整合通訊伺服器至撥號對應表 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-163">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="2afdb-164">若為 Exchange 2010 或最新的 service pack，請參閱 &quot; View Or CONFIGURE UM Server 的屬性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-164">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="2afdb-165">若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-165">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afdb-166">以 SIP 位址設定信箱。</span><span class="sxs-lookup"><span data-stu-id="2afdb-166">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-167">將 SIP 位址指派給將使用 Exchange UM 功能的 Enterprise Voice 使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="2afdb-167">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-168">Lync Server 2013 系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-168">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="2afdb-169">Exchange 收件者系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-169">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="2afdb-170">針對 Exchange 2007 SP1 或最新的 service pack，請參閱 how &quot; To 新增、移除或修改 UM-Enabled 使用者的 SIP 位址 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-170">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="2afdb-171">若為 Exchange 2010 或最新的 service pack，請參閱 &quot; 修改 UM-Enabled 使用者的 SIP 位址 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-171">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="2afdb-172">若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-172">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2afdb-173">執行 exchucutil.ps1 指令碼。</span><span class="sxs-lookup"><span data-stu-id="2afdb-173">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-174">在執行 Exchange UM 服務的伺服器上，開啟 Exchange 管理命令介面，並執行 exchucutil.ps1 腳本，這會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="2afdb-174">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2afdb-175">授與 Lync Server 2013 讀取 Exchange UM Active Directory 網域服務物件（特別是先前任務中建立的 SIP 撥號對應表）的許可權。</span><span class="sxs-lookup"><span data-stu-id="2afdb-175">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="2afdb-176">為主控已啟用 Enterprise Voice 之使用者的每個 Lync Server 2013 Enterprise Edition 集區或 Standard Edition Server 建立 Active Directory 中的整合通訊 IP 閘道物件。</span><span class="sxs-lookup"><span data-stu-id="2afdb-176">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="2afdb-177">為每個閘道建立一個 Exchange UM 群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="2afdb-177">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="2afdb-178">群組搜尋引導識別碼將會是與對應閘道關聯的撥號對應表名稱。</span><span class="sxs-lookup"><span data-stu-id="2afdb-178">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="2afdb-179">如果有多個撥號對應表，則這些項目必須要一一對應。</span><span class="sxs-lookup"><span data-stu-id="2afdb-179">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2afdb-180">Exchange 組織系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-180">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="2afdb-181">Exchange 收件者系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-181">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="2afdb-182"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 上設定 Lync Server 2013 的整合通訊</a></span><span class="sxs-lookup"><span data-stu-id="2afdb-182"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afdb-183">設定 Lync Server 2013 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-183">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-184">若要與 Exchange 2007 SP1 或最新的 service pack （或 Exchange 2010）整合，請建立新的 Enterprise Voice 撥號對應表，並使其名稱符合 Exchange UM 撥號對應表 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="2afdb-184">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="2afdb-185">您必須為每個 UM 撥號對應表執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="2afdb-185">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="2afdb-186">若要與 Exchange 2010 SP1 整合，請確定已設定適當的全域/網站層級或集區層級的 Enterprise Voice 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-186">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="2afdb-187">如果您要與 Exchange 2010 SP1 整合，Lync Server 撥號對應表和 Exchange UM SIP 撥號對應表名稱不需要相符。</span><span class="sxs-lookup"><span data-stu-id="2afdb-187">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="2afdb-188">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2afdb-188">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2afdb-189"><a href="lync-server-2013-configuring-dial-plans.md">在 Lync Server 2013 中設定撥號對應表</a></span><span class="sxs-lookup"><span data-stu-id="2afdb-189"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2afdb-190">執行 Exchange UM 整合工具。</span><span class="sxs-lookup"><span data-stu-id="2afdb-190">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-191">在 Lync Server 2013 上，執行 <strong>ocsumutil.exe</strong>，其：</span><span class="sxs-lookup"><span data-stu-id="2afdb-191">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="2afdb-192">建立「訂戶存取」與「自動語音應答」連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="2afdb-192">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="2afdb-193">驗證是否有符合 Exchange UM 撥號對應表 FQDN 之名稱的 Enterprise Voice 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-193">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="2afdb-194">如果您執行的是 Exchange 2010 SP1 或更新版本，撥號對應表名稱不需要比對，您可以忽略此工具對此的警告。</span><span class="sxs-lookup"><span data-stu-id="2afdb-194">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="2afdb-195">此工具的運作方式是掃描 Exchange UM 設定的 Active Directory，並讓 Lync Server 2013 系統管理員可以查看、建立及編輯連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="2afdb-195">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-196">RTCUniversalServerAdmins <em>與</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2afdb-196">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="2afdb-197">使用者必須同時屬於這兩個群組，ocsumutil.exe 才能順利執行。</span><span class="sxs-lookup"><span data-stu-id="2afdb-197">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="2afdb-198">若要建立連絡人物件，執行 ocsumutil.exe 的使用者對於新連絡人物件存放所在的 Active Directory 組織單位 (OU) 必須具備正確的權限。</span><span class="sxs-lookup"><span data-stu-id="2afdb-198">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="2afdb-199">您可以執行 <STRONG>Grant-CsOUPermission</STRONG> Cmdlet 來授與此許可權。</span><span class="sxs-lookup"><span data-stu-id="2afdb-199">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="2afdb-200">如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。</span><span class="sxs-lookup"><span data-stu-id="2afdb-200">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="2afdb-201"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">設定 Lync Server 2013，以搭配 Microsoft Exchange Server 上的整合通訊使用</a></span><span class="sxs-lookup"><span data-stu-id="2afdb-201"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2afdb-202">如有必要，請執行其他企業語音設定步驟。</span><span class="sxs-lookup"><span data-stu-id="2afdb-202">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-203">如果您尚未設定伺服器或使用者的企業語音設定，請執行下列一或多項作業：</span><span class="sxs-lookup"><span data-stu-id="2afdb-203">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2afdb-204">部署和設定</span><span class="sxs-lookup"><span data-stu-id="2afdb-204">Deploy and configure</span></span></p>
<p><span data-ttu-id="2afdb-205">公用交換電話網路 (PSTN) 閘道和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="2afdb-205">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="2afdb-206">定義語音原則、PSTN 使用方式記錄與撥出電話路由。</span><span class="sxs-lookup"><span data-stu-id="2afdb-206">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="2afdb-207">啟用使用者的企業語音。</span><span class="sxs-lookup"><span data-stu-id="2afdb-207">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="2afdb-208">(選擇性) 設定特定使用者的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="2afdb-208">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="2afdb-209">視您所啟用的企業語音功能之不同，您可能必須執行其他設定步驟。</span><span class="sxs-lookup"><span data-stu-id="2afdb-209">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-210">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2afdb-210">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2afdb-211">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2afdb-211">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2afdb-212">請參閱以下幾節中的主題：</span><span class="sxs-lookup"><span data-stu-id="2afdb-212">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="2afdb-213"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由</a></span><span class="sxs-lookup"><span data-stu-id="2afdb-213"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="2afdb-214"><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企業語音</a></span><span class="sxs-lookup"><span data-stu-id="2afdb-214"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2afdb-215">啟用 Exchange UM 的 Enterprise Voice 使用者。</span><span class="sxs-lookup"><span data-stu-id="2afdb-215">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-216">在 Exchange UM 伺服器上，確定已建立整合通訊信箱原則，且每位使用者都有唯一的分機號碼指派，然後為使用者啟用整合通訊。</span><span class="sxs-lookup"><span data-stu-id="2afdb-216">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="2afdb-217">Exchange 收件者系統管理員</span><span class="sxs-lookup"><span data-stu-id="2afdb-217">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="2afdb-218">若為 Exchange 2007 SP1 或最新的 service pack，請參閱 how &quot; To Enable a User for a 整合通訊 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-218">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="2afdb-219">針對 Exchange 2010 或最新的 service pack，請參閱 &quot; Enable a User for a 整合通訊 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-219">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="2afdb-220">若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</span><span class="sxs-lookup"><span data-stu-id="2afdb-220">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

