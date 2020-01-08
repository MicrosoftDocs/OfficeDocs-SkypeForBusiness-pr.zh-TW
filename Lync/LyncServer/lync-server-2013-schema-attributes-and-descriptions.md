---
title: Lync Server 2013：架構屬性和描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="cc246-102">Lync Server 2013 中的架構屬性和描述</span><span class="sxs-lookup"><span data-stu-id="cc246-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc246-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="cc246-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="cc246-104">本節將說明 Lync Server 2013 使用的所有架構屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="cc246-105">針對與屬性相關聯的類別，請參閱[Lync Server 2013 中的 [依類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)]。</span><span class="sxs-lookup"><span data-stu-id="cc246-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="cc246-106">如需 Lync Server 2013 中新類別和屬性的清單，請參閱[Lync server 2013 中的架構變更](lync-server-2013-schema-changes-in-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="cc246-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="cc246-107">連結對的屬性會指定為轉寄連結或返回連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="cc246-108">參照另一個物件的屬性是轉寄連結;參照第一個物件的另一個物件屬性是 [上一頁] 連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="cc246-109">[轉寄] 連結是可更新的，而 [返回] 連結則是唯讀的。</span><span class="sxs-lookup"><span data-stu-id="cc246-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="cc246-110">有些屬性有位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="cc246-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="cc246-111">針對這些屬性，每個設定都是由一個位來表示，而顯示的十進位值代表位位置。</span><span class="sxs-lookup"><span data-stu-id="cc246-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="cc246-112">位位置從位0開始。</span><span class="sxs-lookup"><span data-stu-id="cc246-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="cc246-113">例如，1（binary）為 bit 0，而10000（binary）為 bit 4。</span><span class="sxs-lookup"><span data-stu-id="cc246-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="cc246-114">每個位代表一個屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-114">Each bit represents a property.</span></span> <span data-ttu-id="cc246-115">以下是一些範例：</span><span class="sxs-lookup"><span data-stu-id="cc246-115">The following are some examples:</span></span>

  - <span data-ttu-id="cc246-116">10000（binary）的十進位值是16（也就是位4已設定）。</span><span class="sxs-lookup"><span data-stu-id="cc246-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="cc246-117">100000000（binary）的十進位值是256（也就是已設定位8）。</span><span class="sxs-lookup"><span data-stu-id="cc246-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="cc246-118">1100（binary）的十進位值是12（也就是設定的位2和 3; 兩位都已啟用）。</span><span class="sxs-lookup"><span data-stu-id="cc246-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="cc246-119">1111000001（binary）的十進位值是961（也就是位0、6、7、8和9）; 每個這些位的屬性都已啟用。</span><span class="sxs-lookup"><span data-stu-id="cc246-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="cc246-120">Lync Server 2013 的架構屬性</span><span class="sxs-lookup"><span data-stu-id="cc246-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc246-121">Attribute</span><span class="sxs-lookup"><span data-stu-id="cc246-121">Attribute</span></span></th>
<th><span data-ttu-id="cc246-122">描述</span><span class="sxs-lookup"><span data-stu-id="cc246-122">Description</span></span></th>
<th><span data-ttu-id="cc246-123">批註</span><span class="sxs-lookup"><span data-stu-id="cc246-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc246-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="cc246-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="cc246-125">Active Directory 網域服務中現有的屬性，現在與<strong>msRTCSIP-Pool</strong>和<strong>msRTCSIP MonitoringServer</strong>類別相關聯。</span><span class="sxs-lookup"><span data-stu-id="cc246-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="cc246-126">這個屬性會指定池或監視伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="cc246-127">每個區段的有效值為63字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="cc246-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="cc246-128">Microsoft Office Live 通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-129">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="cc246-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="cc246-130">這個屬性包含與這個物件相對應之另一個目錄林中之物件辨識名稱（DN）的字串標記法。</span><span class="sxs-lookup"><span data-stu-id="cc246-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="cc246-131">這個屬性是用於通訊群組延伸及自動出席。</span><span class="sxs-lookup"><span data-stu-id="cc246-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="cc246-132">這個屬性是在 Windows Server 2003 R2 的預設 Active Directory 架構中定義。</span><span class="sxs-lookup"><span data-stu-id="cc246-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="cc246-133">若要避免需要將 AD DS 升級至 Windows Server 2003 R2，Active Directory 架構準備會將 Windows Server 2003 架構與此屬性定義延伸。</span><span class="sxs-lookup"><span data-stu-id="cc246-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="cc246-134">Microsoft Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="cc246-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="cc246-136">這個多重值屬性會儲存語音信箱設定。</span><span class="sxs-lookup"><span data-stu-id="cc246-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="cc246-137">這個屬性會與 Exchange 整合通訊（UM）共用。</span><span class="sxs-lookup"><span data-stu-id="cc246-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="cc246-138">Microsoft Lync Server 2010 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="cc246-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="cc246-140">這個多重值屬性包含適用于使用者的保留原則的識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="cc246-141">保留原則在保留期間保留使用者的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="cc246-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="cc246-142">這個屬性是與 Exchange 2013 共用的。</span><span class="sxs-lookup"><span data-stu-id="cc246-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="cc246-143">Lync Server 2013 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="cc246-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="cc246-145">這個屬性會儲存使用者的音訊會議提供者資訊。</span><span class="sxs-lookup"><span data-stu-id="cc246-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="cc246-146">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="cc246-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="cc246-148">這個屬性指向應用程式連絡人的信任服務專案。</span><span class="sxs-lookup"><span data-stu-id="cc246-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="cc246-149">Microsoft Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="cc246-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="cc246-151">這個屬性包含應用程式伺服器上已託管的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="cc246-152">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="cc246-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="cc246-154">這個屬性指定應用程式連絡人的選項。</span><span class="sxs-lookup"><span data-stu-id="cc246-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="cc246-155">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="cc246-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="cc246-157">這個屬性包含應用程式連絡人的主要語言。</span><span class="sxs-lookup"><span data-stu-id="cc246-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="cc246-158">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="cc246-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="cc246-160">這個多重值屬性包含應用程式連絡人的次要語言。</span><span class="sxs-lookup"><span data-stu-id="cc246-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="cc246-161">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="cc246-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="cc246-163">這個屬性包含屬於這個 pool 的應用程式伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="cc246-164">此 back link 屬性的相對應轉寄連結為<strong>msRTCSIP-ApplicationServerPoolLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-165">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="cc246-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="cc246-167">這個屬性會指向該應用程式伺服器所屬的池。</span><span class="sxs-lookup"><span data-stu-id="cc246-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="cc246-168">這是 [轉寄] 連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-168">This is the forward link.</span></span> <span data-ttu-id="cc246-169">對應的 [向後] 連結為<strong>msRTCSIP-ApplicationServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-170">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-171">msRTCSIP-ArchiveDefault （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-172">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-173">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-174">msRTCSIP-ArchiveDefaultFlags （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-175">這個屬性會指定林邊界內的全域預設值，以封存所有的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="cc246-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="cc246-176">這是由 [存檔代理程式] 層級強制執行。</span><span class="sxs-lookup"><span data-stu-id="cc246-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="cc246-177">此屬性的值範圍如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-178"><strong>TRUE</strong>：封存所有使用者</span><span class="sxs-lookup"><span data-stu-id="cc246-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="cc246-179"><strong>FALSE</strong>：不封存所有使用者</span><span class="sxs-lookup"><span data-stu-id="cc246-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="cc246-180">這個屬性在林邊界內，全域控制如何將內部網路中的使用者通訊歸檔。</span><span class="sxs-lookup"><span data-stu-id="cc246-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="cc246-181"><strong>即時通訊伺服器2005行為（現已停用）</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="cc246-182">此屬性的值範圍如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-183">0：封存郵件正文 [bit 0]</span><span class="sxs-lookup"><span data-stu-id="cc246-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="cc246-184">1：不要封存郵件本文的內容 [bit 0]</span><span class="sxs-lookup"><span data-stu-id="cc246-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="cc246-185"><strong>Office 通訊伺服器2007行為</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="cc246-186">此屬性的值範圍如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-187">0： ArchiveFederationDefaultWithoutBody （已停用）</span><span class="sxs-lookup"><span data-stu-id="cc246-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="cc246-188">1-2： ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="cc246-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="cc246-189">3-4： ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="cc246-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="cc246-190">5： RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="cc246-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="cc246-191">6： RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="cc246-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="cc246-192">7： RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="cc246-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="cc246-193">8： RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="cc246-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="cc246-194">9： RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="cc246-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="cc246-195">10： RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="cc246-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="cc246-196">11： RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="cc246-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="cc246-197">12： RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="cc246-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="cc246-198">13： RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="cc246-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="cc246-199">14： RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="cc246-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="cc246-200">15： RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="cc246-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="cc246-201">16： RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="cc246-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-202">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-203">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-204">msRTCSIP-ArchiveFederationDefault （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-205">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-206">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-207">msRTCSIP-ArchiveFederationDefaultFlags （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-208">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-209">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="cc246-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="cc246-211">這個屬性是一個整數，用來做為位欄位，以控制是否要封存單一使用者的通訊。</span><span class="sxs-lookup"><span data-stu-id="cc246-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="cc246-212">此控制項是由 [存檔代理程式] 層級強制執行。</span><span class="sxs-lookup"><span data-stu-id="cc246-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="cc246-213">它標示為供全域編目複製。</span><span class="sxs-lookup"><span data-stu-id="cc246-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="cc246-214">這個屬性的範圍是針對單一使用者或連絡人。</span><span class="sxs-lookup"><span data-stu-id="cc246-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="cc246-215">Lync Server 中的有效值（以及相關聯的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-216">0：不封存（沒有位組）</span><span class="sxs-lookup"><span data-stu-id="cc246-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="cc246-217">1：已停用（位位置0）</span><span class="sxs-lookup"><span data-stu-id="cc246-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="cc246-218">2：已停用（位位置1）</span><span class="sxs-lookup"><span data-stu-id="cc246-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="cc246-219">4：封存內部通訊（位位置2）</span><span class="sxs-lookup"><span data-stu-id="cc246-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="cc246-220">8：封存聯盟通訊（位位置3）</span><span class="sxs-lookup"><span data-stu-id="cc246-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="cc246-221">在即時通訊伺服器2005中先前有效的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-222">0：使用<strong>msRTCSIP-ArchiveDefault</strong>和<strong>msRTCSIP-ArchiveFederation</strong>所定義的預設值，並以下列優先順序順序排列：</span><span class="sxs-lookup"><span data-stu-id="cc246-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-223">1：封存</span><span class="sxs-lookup"><span data-stu-id="cc246-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="cc246-224">2：不要封存</span><span class="sxs-lookup"><span data-stu-id="cc246-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="cc246-225">3：不含郵件正文的封存</span><span class="sxs-lookup"><span data-stu-id="cc246-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="cc246-226">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-227">msRTCSIP-ArchivingServerData （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-228">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-229">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-230">msRTCSIP-ArchivingServerVersion （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-231">這個屬性會定義 [存檔服務] 的版本。</span><span class="sxs-lookup"><span data-stu-id="cc246-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="cc246-232">這個屬性是一種 monotonously 增加的整數類型，每個正式產品發行都會增加。</span><span class="sxs-lookup"><span data-stu-id="cc246-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="cc246-233">可能的有效值為：</span><span class="sxs-lookup"><span data-stu-id="cc246-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-234">未定義：即時通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="cc246-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="cc246-235">                 [即時通訊伺服器] 2005</span><span class="sxs-lookup"><span data-stu-id="cc246-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="cc246-236">                 使用 SP1 進行即時通訊伺服器2005</span><span class="sxs-lookup"><span data-stu-id="cc246-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="cc246-237">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="cc246-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="cc246-238">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cc246-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-239">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-240">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="cc246-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="cc246-242">這個屬性會指定池後端伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cc246-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="cc246-243">因為每個池只能有一個後端伺服器，所以這是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="cc246-244">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="cc246-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="cc246-245">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="cc246-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="cc246-247">這個屬性包含主持會議目錄之池的識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="cc246-248">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="cc246-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="cc246-250">這個屬性包含會議目錄的識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="cc246-251">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="cc246-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="cc246-253">這個屬性包含要將會議目錄移到哪個池的識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="cc246-254">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-255">msRTCSIP-預設值</span><span class="sxs-lookup"><span data-stu-id="cc246-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="cc246-256">這個布林值屬性可定義電話使用方式是否為預設用法。</span><span class="sxs-lookup"><span data-stu-id="cc246-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="cc246-257">如果此屬性設定為<strong>TRUE</strong>，系統會使用電話的預設使用量，且無法由系統管理員刪除。</span><span class="sxs-lookup"><span data-stu-id="cc246-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="cc246-258">如果此屬性設定為<strong>FALSE</strong>，則可以刪除此用法。</span><span class="sxs-lookup"><span data-stu-id="cc246-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="cc246-259">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="cc246-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="cc246-261">這個屬性會針對組織外的使用者識別 Communicator Web 存取 URL。</span><span class="sxs-lookup"><span data-stu-id="cc246-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="cc246-262">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="cc246-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="cc246-264">這個屬性會針對組織內的使用者識別 Communicator Web 存取 URL。</span><span class="sxs-lookup"><span data-stu-id="cc246-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="cc246-265">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-266">msRTCSIP-DefaultLocationProfileLink （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-267">這個單一值屬性包含指派給它之位置設定檔類別物件的辨識名稱（DN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="cc246-268">轉寄連結：<strong>連結識別碼 11036</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="cc246-269">對應的 [向後] 連結為<strong>msRTCSIP-ServerReferenceBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-270">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-271">msRTCSIP-DefaultPolicy （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-272">這個布林屬性指定原則是否為預設原則。</span><span class="sxs-lookup"><span data-stu-id="cc246-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="cc246-273">原則是設定為<strong>TRUE</strong>時的預設原則。</span><span class="sxs-lookup"><span data-stu-id="cc246-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-274">Office 通訊伺服器2007中的新功能</span><span class="sxs-lookup"><span data-stu-id="cc246-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="cc246-275">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-276">msRTCSIP-DefaultRouteToEdgeProxy （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-277">這個屬性會指定執行存取邊緣服務的邊緣伺服器（如果可以直接存取）或硬體負載平衡器（在執行 Access Edge 服務的伺服器池中）的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cc246-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="cc246-278">如果只能透過一或多個控制器存取執行存取邊緣服務的伺服器，這個屬性會指定 FQDN，以及（也可以選擇）控制器的埠號碼，或硬體負載平衡器為主管池提供服務。</span><span class="sxs-lookup"><span data-stu-id="cc246-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="cc246-279">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="cc246-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="cc246-280">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-281">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-282">msRTCSIP-DefaultRouteToEdgeProxyPort （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-283">這個屬性代表應該用來連線到執行存取邊緣服務之伺服器的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="cc246-284">有效的值是指定要使用的埠的整數值。</span><span class="sxs-lookup"><span data-stu-id="cc246-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="cc246-285">預設值為5061。</span><span class="sxs-lookup"><span data-stu-id="cc246-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="cc246-286">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-287">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-288">msRTCSIP-DefPresenceSubscriptionTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-289">這個屬性代表預設的目前狀態訂閱超時期間。</span><span class="sxs-lookup"><span data-stu-id="cc246-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="cc246-290">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-291">msRTCSIP-DefRegistrationTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-292">這個屬性代表預設的 [註冊超時] 視窗。</span><span class="sxs-lookup"><span data-stu-id="cc246-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="cc246-293">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-294">msRTCSIP-DefRoamingDataSubscriptionTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-295">這個屬性代表預設的 [漫遊資料訂閱超時] 視窗。</span><span class="sxs-lookup"><span data-stu-id="cc246-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="cc246-296">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="cc246-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="cc246-298">這個屬性是在分割網域拓撲中使用，並包含完全限定的功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="cc246-299">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-300">msRTCSIP-描述（已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-301">這個單一值的 UNICODE 字串屬性包含此手機路由或正常化規則的助記描述。</span><span class="sxs-lookup"><span data-stu-id="cc246-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="cc246-302">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-303">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="cc246-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="cc246-305">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-306">msRTCSIP-功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="cc246-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="cc246-307">這個屬性代表為註冊機構設定的網域。</span><span class="sxs-lookup"><span data-stu-id="cc246-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="cc246-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="cc246-309">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-310">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="cc246-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="cc246-312">這個屬性會指定執行存取邊緣服務之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cc246-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="cc246-313">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="cc246-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="cc246-314">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-315">msRTCSIP-EnableBestEffortNotify （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-316">這個屬性控制伺服器是否會產生最佳努力通知（BENOTIFY）要求，而不是通知要求，以回應來自用戶端的訂閱要求。</span><span class="sxs-lookup"><span data-stu-id="cc246-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="cc246-317">BENOTIFY 是伺服器產生 BENOTIFY 要求而不是一般通知要求的 [訂閱通知握手] 延伸的效能。</span><span class="sxs-lookup"><span data-stu-id="cc246-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="cc246-318">效能好處是 BENOTIFY 要求不需要用戶端的 200 OK 回應，就像是通知要求。</span><span class="sxs-lookup"><span data-stu-id="cc246-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="cc246-319">有效值為<strong>TRUE</strong>或<strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cc246-320">[即時通訊伺服器] 2003 不支援 BENOTIFY 要求。</span><span class="sxs-lookup"><span data-stu-id="cc246-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="cc246-321">若要與在即時通訊2005伺服器上執行的即時通訊伺服器2003伺服器 API （以及協力廠商伺服器）所撰寫的伺服器應用程式交互操作，可以透過將 BENOTIFY 要求設定為<STRONG>FALSE</STRONG>來加以停用。</span><span class="sxs-lookup"><span data-stu-id="cc246-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="cc246-322">BENOTIFY 目前不是 IETF （網際網路工程工作強制） SIP 標準化處理常式的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc246-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="cc246-323">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-324">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-325">msRTCSIP-EnableFederation （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-326">這個屬性是一個全域開關，IT 系統管理員會使用它來設定是否允許使用者與其他組織的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="cc246-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="cc246-327">它可讓系統管理員覆寫個別使用者的<strong>FederationEnabled</strong>屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="cc246-328">此屬性可讓您協助保護內部網路，避免受到公司的蠕蟲、病毒或目標攻擊所造成的網際網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="cc246-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="cc246-329">有效值（以及相關聯的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-330">1：啟用公用 IM 連線（位位置0）</span><span class="sxs-lookup"><span data-stu-id="cc246-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="cc246-331">2：保留（bit 位置1）</span><span class="sxs-lookup"><span data-stu-id="cc246-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="cc246-332">4：保留（bit 位置2）</span><span class="sxs-lookup"><span data-stu-id="cc246-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="cc246-333">8：保留（bit 位置3）</span><span class="sxs-lookup"><span data-stu-id="cc246-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="cc246-334">16：已啟用遠端呼叫控制 [電話] （位位置4）</span><span class="sxs-lookup"><span data-stu-id="cc246-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="cc246-335">64： AllowOrganizeMeetingWithAnonymousParticipants （允許使用者邀請匿名使用者加入會議（位位置6）</span><span class="sxs-lookup"><span data-stu-id="cc246-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="cc246-336">128： UCEnabled （可讓使用者進行整合通訊）（位位置7）</span><span class="sxs-lookup"><span data-stu-id="cc246-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="cc246-337">256： EnabledForEnhancedPresence （可讓使用者使用公用 IM 連線）（bit 位置8）</span><span class="sxs-lookup"><span data-stu-id="cc246-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="cc246-338">512： RemoteCallControlDualMode （bit 位置9）</span><span class="sxs-lookup"><span data-stu-id="cc246-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-339">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-340">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="cc246-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="cc246-342">這個屬性會指出是否要在指定的伺服器上載入企業服務。</span><span class="sxs-lookup"><span data-stu-id="cc246-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="cc246-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="cc246-344">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="cc246-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="cc246-346">這個屬性包含外部存取的撥號程式碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="cc246-347">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="cc246-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="cc246-349">這個屬性控制是否針對單一使用者啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="cc246-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="cc246-350">它是由 [企業服務] 層強制執行。</span><span class="sxs-lookup"><span data-stu-id="cc246-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="cc246-351">它標示為供全域編目複製。</span><span class="sxs-lookup"><span data-stu-id="cc246-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="cc246-352">有效值為<strong>TRUE</strong>或<strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-353">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="cc246-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="cc246-355">這個屬性是一個多重值清單，其中包含與某個池關聯的所有企業版伺服器的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cc246-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="cc246-356">返回連結：<strong>連結識別碼 11023</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="cc246-357">此返回連結的相對前連結是<strong>msRTCSIP-PoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-358">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-359">msRTCSIP-閘道（已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-360">這個多重值字串屬性包含閘道和埠的清單（每個閘道）。</span><span class="sxs-lookup"><span data-stu-id="cc246-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="cc246-361">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-362">msRTCSIP-GlobalSettingsData （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-363">這個屬性會儲存 [名稱：值] 對。</span><span class="sxs-lookup"><span data-stu-id="cc246-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="cc246-364">已定義的名稱：值對適用于 [<strong>允許輪詢目前狀態</strong>] 設定。</span><span class="sxs-lookup"><span data-stu-id="cc246-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="cc246-365">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="cc246-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="cc246-367">這個屬性是用來群組通訊錄專案之群組的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="cc246-368">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-369">msRTCSIP-HomeServer （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-370">即時通訊伺服器2003中的新功能（不使用）。</span><span class="sxs-lookup"><span data-stu-id="cc246-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="cc246-371">在即時通訊伺服器2005中過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-372">msRTCSIP-HomeServerString （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-373">即時通訊伺服器2003中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="cc246-374">在即時通訊伺服器2005中過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-375">msRTCSIP-HomeUsers （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-376">即時通訊伺服器2003中的新功能（不使用）。</span><span class="sxs-lookup"><span data-stu-id="cc246-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="cc246-377">在即時通訊伺服器2005中過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="cc246-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="cc246-379">這個屬性控制是否已針對外部使用者存取啟用單一使用者。</span><span class="sxs-lookup"><span data-stu-id="cc246-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="cc246-380">它是由 [企業服務] 層強制執行。</span><span class="sxs-lookup"><span data-stu-id="cc246-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="cc246-381">它標示為供全域編目複製。</span><span class="sxs-lookup"><span data-stu-id="cc246-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="cc246-382">有效值為<strong>TRUE</strong>或<strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-383">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-384">msRTCSIP-IsMaster （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-385">即時通訊伺服器2003中的新功能</span><span class="sxs-lookup"><span data-stu-id="cc246-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="cc246-386">在即時通訊伺服器2005中過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-387">msRTCSIP 線</span><span class="sxs-lookup"><span data-stu-id="cc246-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="cc246-388">這個單一值屬性包含 Lync for 電話語音所使用的裝置識別碼（SIP URI 或使用者控制項電話的電話 URI）。</span><span class="sxs-lookup"><span data-stu-id="cc246-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="cc246-389">這個屬性標示為供全域編目複製，且已編制索引。</span><span class="sxs-lookup"><span data-stu-id="cc246-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="cc246-390">如果使用者已啟用企業語音，此屬性會儲存以164標準形式的使用者電話號碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="cc246-391">Microsoft Office Live 通訊伺服器2005中的新功能（含 SP1）</span><span class="sxs-lookup"><span data-stu-id="cc246-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="cc246-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="cc246-393">這個單值屬性包含 CSTA-SIP 閘道伺服器的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="cc246-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="cc246-394">這個屬性標示為 [全域編目複製]，但未編制索引。</span><span class="sxs-lookup"><span data-stu-id="cc246-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="cc246-395">Microsoft Office Live 通訊伺服器2005中的新功能（含 SP1）</span><span class="sxs-lookup"><span data-stu-id="cc246-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-396">msRTCSIP-LocalNormalizationData （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-397">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-398">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-399">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-400">msRTCSIP-LocalNormalizationLinks （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-401">這個多重值屬性包含與此位置設定檔相關聯的局部正常化可分辨名稱（DN）清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="cc246-402">這個屬性的類型是 DN 二進位。</span><span class="sxs-lookup"><span data-stu-id="cc246-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="cc246-403">位置設定檔與局部正常化規則之間有一對多的關聯性。</span><span class="sxs-lookup"><span data-stu-id="cc246-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="cc246-404">局部正常化 DNs 清單的排序必須依管理員指定的順序進行維護。</span><span class="sxs-lookup"><span data-stu-id="cc246-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="cc246-405">順序保留是由 DN 二進位的二進位部分所維護，它會指定訂單索引。</span><span class="sxs-lookup"><span data-stu-id="cc246-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="cc246-406">轉寄連結：<strong>連結識別碼 11034</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="cc246-407">與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-LocationProfileBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-408">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-409">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="cc246-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="cc246-411">這個屬性包含正常化規則選項的清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="cc246-412">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-413">msRTCSIP-LocationName （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-414">這個單一值屬性包含位置設定檔的易記名稱，指出此設定檔代表的位置。</span><span class="sxs-lookup"><span data-stu-id="cc246-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="cc246-415">因為可能有多個位置設定檔，所以管理員需要一種方式來區分不同的設定檔。</span><span class="sxs-lookup"><span data-stu-id="cc246-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="cc246-416">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-417">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-418">msRTCSIP-locationProfileBL （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-419">這個多重值屬性包含位置設定檔辨識名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="cc246-420">這個屬性會指定一個或多個位置設定檔的上一頁連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="cc246-421">返回連結：<strong>連結識別碼 11035</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="cc246-422">這個屬性會對應到轉寄連結<strong>msRTCSIP-LocalNormalizationLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-423">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-424">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-425">msRTCSIP-LocationProfileData （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-426">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-427">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-428">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="cc246-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="cc246-430">這個屬性包含位置設定檔的選項。</span><span class="sxs-lookup"><span data-stu-id="cc246-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="cc246-431">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="cc246-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="cc246-433">這個多重值屬性會保留應用程式連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="cc246-434">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="cc246-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="cc246-436">這個多重值屬性會保留位置設定檔的清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="cc246-437">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-438">msRTCSIP-MaxNumOutstandingSearchPerServer （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-439">這個屬性代表每個伺服器上未處理的搜尋要求數目上限。</span><span class="sxs-lookup"><span data-stu-id="cc246-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="cc246-440">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-441">msRTCSIP-MaxNumSubscriptionsPerUser （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-442">屬性代表每個使用者的訂閱數上限。</span><span class="sxs-lookup"><span data-stu-id="cc246-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="cc246-443">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-444">msRTCSIP-MaxPresenceSubscriptionTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-445">這個屬性代表 [訂閱超時] 視窗的最大值。</span><span class="sxs-lookup"><span data-stu-id="cc246-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="cc246-446">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-447">msRTCSIP-MaxRegistrationsTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-448">這個屬性代表 [最大註冊超時] 視窗。</span><span class="sxs-lookup"><span data-stu-id="cc246-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="cc246-449">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-451">這個屬性代表最大的 [漫遊資料訂閱超時] 視窗。</span><span class="sxs-lookup"><span data-stu-id="cc246-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="cc246-452">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="cc246-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="cc246-454">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-455">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="cc246-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="cc246-457">這個屬性是電腦類別下的服務控制點屬性，可指定連結回到它所屬的 multipoint 控制項單元（MCU）工廠。</span><span class="sxs-lookup"><span data-stu-id="cc246-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="cc246-458">針對每個 Microsoft MCU，都會建立此服務控制點和屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="cc246-459">每個 Microsoft MCU 都必須找到它所屬之池的後端伺服器，才能從它取得池層級設定。</span><span class="sxs-lookup"><span data-stu-id="cc246-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="cc246-460">這個屬性的值是 MCU 工廠的辨識名稱（DN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="cc246-461">這是單值屬性，並標示為供全域編目複製。</span><span class="sxs-lookup"><span data-stu-id="cc246-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="cc246-462">轉寄連結：<strong>連結識別碼 11026</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="cc246-463">與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-MCUServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-464">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="cc246-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="cc246-466">這是多重字串保留屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="cc246-467">儲存在這個屬性中的設定會以名稱 = 值對表示。</span><span class="sxs-lookup"><span data-stu-id="cc246-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="cc246-468">目前定義的名稱 = 值對：</span><span class="sxs-lookup"><span data-stu-id="cc246-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="cc246-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-470">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="cc246-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="cc246-472">這個單一值屬性包含與某個池相關聯的單一 MCU 工廠的辨識名稱（DN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="cc246-473">轉寄連結：<strong>連結識別碼 11024</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="cc246-474">與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-PoolAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-475">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="cc246-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="cc246-477">這個屬性是一個指定 MCU 工廠提供者的 GUID 的單一值字串。</span><span class="sxs-lookup"><span data-stu-id="cc246-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="cc246-478">根據 GUID 值，MCU factory 進程會判斷是否要為此 MCU 類型服務。</span><span class="sxs-lookup"><span data-stu-id="cc246-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="cc246-479">如果 GUID 值是<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，則 MCU factory 程式（在 Lync Server 中則預設提供）會處理它。</span><span class="sxs-lookup"><span data-stu-id="cc246-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="cc246-480">對於任何其他 GUID 值，MCU factory 進程將不會為 MCU 類型提供服務。</span><span class="sxs-lookup"><span data-stu-id="cc246-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="cc246-481">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="cc246-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="cc246-483">這個屬性是一個多重值清單，可分辨名稱（DN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="cc246-484">這個屬性包含與此 MCU 工廠相關聯之相同類型和廠商的所有 MCU 伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="cc246-485">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="cc246-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="cc246-486">返回連結：連結識別碼11027</span><span class="sxs-lookup"><span data-stu-id="cc246-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="cc246-487">此返回連結的相對前連結是<strong>msRTCSIP-MCUFactoryAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-488">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="cc246-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="cc246-490">這個屬性是單一值字串，它指定了 MCU 可以處理的媒介。</span><span class="sxs-lookup"><span data-stu-id="cc246-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="cc246-491">支援的有效類型包括：</span><span class="sxs-lookup"><span data-stu-id="cc246-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-492">要求</span><span class="sxs-lookup"><span data-stu-id="cc246-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="cc246-493">音訊-影片</span><span class="sxs-lookup"><span data-stu-id="cc246-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="cc246-494">交流</span><span class="sxs-lookup"><span data-stu-id="cc246-494">chat</span></span></p></li>
<li><p><span data-ttu-id="cc246-495">電話會議</span><span class="sxs-lookup"><span data-stu-id="cc246-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-496">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="cc246-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="cc246-498">這個屬性是指定 MCU 廠商名稱的單一值字串。</span><span class="sxs-lookup"><span data-stu-id="cc246-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="cc246-499">所有 Microsoft MCUs 都會將這個屬性指定為<strong>Microsoft Corporation</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-500">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-501">msRTCSIP-MeetingFlags （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-502">這個屬性會定義不同的會議選項，這些選項會針對所有使用者或連絡人物件全域啟用。</span><span class="sxs-lookup"><span data-stu-id="cc246-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="cc246-503">這個屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="cc246-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="cc246-504">有效值（以及相關聯的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-505">0： AllowOrganizeMeetingWithAnonymousParticipants 為 None （不允許使用者邀請匿名使用者加入會議）（未設定位）</span><span class="sxs-lookup"><span data-stu-id="cc246-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="cc246-506">4： AllowOrganizeMeetingWithAnonymousParticipants 為 [所有人] （允許所有使用者邀請匿名使用者加入會議）（位位置2）</span><span class="sxs-lookup"><span data-stu-id="cc246-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="cc246-507">8： AllowOrganizeMeetingWithAnonymousParticipants 是 UsePerUserSetting （允許使用者根據每個使用者設定邀請匿名使用者加入會議）（位位置3）</span><span class="sxs-lookup"><span data-stu-id="cc246-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="cc246-508">16： UserPerUserMeetingPolicy （會議原則是針對每位使用者定義）（bit 位置4）</span><span class="sxs-lookup"><span data-stu-id="cc246-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-509">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-510">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-511">msRTCSIP-MeetingPolicy （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-512">這個屬性會指定管理員指派給此使用者做為單一值屬性之原則的辨識名稱（DN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="cc246-513">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-514">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-515">msRTCSIP-MinPresenceSubscriptionTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-516">這個屬性代表最小的目前狀態訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="cc246-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="cc246-517">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-518">msRTCSIP-MinRegistrationTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-519">這個屬性代表最小的註冊超時視窗。</span><span class="sxs-lookup"><span data-stu-id="cc246-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="cc246-520">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-521">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-522">msRTCSIP-MinRoamingDataSubscriptionTimeout （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-523">這個屬性代表最小的 [漫遊資料訂閱超時] 視窗。</span><span class="sxs-lookup"><span data-stu-id="cc246-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="cc246-524">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-525">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="cc246-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="cc246-527">這個屬性是用來儲存前端池所使用的鏡像 SQL Server 後端。</span><span class="sxs-lookup"><span data-stu-id="cc246-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="cc246-528">Lync Server 2013 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="cc246-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="cc246-530">這個屬性包含定義行動設定的選項和標誌。</span><span class="sxs-lookup"><span data-stu-id="cc246-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="cc246-531">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="cc246-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="cc246-533">這個屬性包含行動策略物件的 DN。</span><span class="sxs-lookup"><span data-stu-id="cc246-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="cc246-534">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-535">msRTCSIP-NumDevicesPerUser （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-536">這個屬性代表允許使用者註冊 SIP 通訊及訂閱目前狀態的裝置數量。</span><span class="sxs-lookup"><span data-stu-id="cc246-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="cc246-537">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-538">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="cc246-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="cc246-540">這個屬性會指定為使用者或連絡人物件啟用的選項。</span><span class="sxs-lookup"><span data-stu-id="cc246-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="cc246-541">這個屬性是 integer 類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="cc246-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="cc246-542">每個選項都是由一個位來表示。</span><span class="sxs-lookup"><span data-stu-id="cc246-542">Each option is represented by a bit.</span></span> <span data-ttu-id="cc246-543">這個屬性標示為供全域編目複製。</span><span class="sxs-lookup"><span data-stu-id="cc246-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="cc246-544">有效值（以及相關聯的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-545">1：啟用公用立即訊息（IM）連線（位位置0）</span><span class="sxs-lookup"><span data-stu-id="cc246-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="cc246-546">2：保留（bit 位置1）</span><span class="sxs-lookup"><span data-stu-id="cc246-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="cc246-547">4：保留（bit 位置2）</span><span class="sxs-lookup"><span data-stu-id="cc246-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="cc246-548">8：保留（bit 位置3）</span><span class="sxs-lookup"><span data-stu-id="cc246-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="cc246-549">16：已啟用遠端呼叫控制 [電話] （位位置4）</span><span class="sxs-lookup"><span data-stu-id="cc246-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="cc246-550">64： AllowOrganizeMeetingWithAnonymousParticipants （允許使用者邀請匿名使用者加入會議（位位置6）</span><span class="sxs-lookup"><span data-stu-id="cc246-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="cc246-551">128： UCEnabled （啟用 UC 的使用者）（位位置7）</span><span class="sxs-lookup"><span data-stu-id="cc246-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="cc246-552">256： EnabledForEnhancedPresence （可讓使用者使用公用 IM 連線）（bit 位置8）</span><span class="sxs-lookup"><span data-stu-id="cc246-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="cc246-553">512： RemoteCallControlDualMode （bit 位置9）</span><span class="sxs-lookup"><span data-stu-id="cc246-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-554">即時通訊伺服器2005中的新功能（含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="cc246-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="cc246-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="cc246-556">這個屬性是在資源與中央林拓撲中使用，可在從 Windows NT 伺服器主體帳戶將使用者的 ObjectSID 複製到資源或中央林中的對應使用者或連絡人物件的這個屬性時，啟用單一登入。</span><span class="sxs-lookup"><span data-stu-id="cc246-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="cc246-557">Communicator Web Access 會使用這個屬性或使用者的 ObjectSID，在 AD DS 中搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="cc246-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="cc246-558">這個屬性標示為供全域編目複製。</span><span class="sxs-lookup"><span data-stu-id="cc246-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="cc246-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="cc246-560">這個屬性是應用程式連絡人擁有者的統一資源名稱（URN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="cc246-561">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-562">msRTCSIP-模式（已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-563">這個單值字串屬性包含一個模式，用於將撥號號碼與 E. 164 格式搭配使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="cc246-564">如果撥號號碼符合這個模式，就會將轉換套用到撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="cc246-565">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-566">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-567">msRTCSIP-PhoneRouteBL （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-568">這個多重值屬性包含一份電話路線可分辨名稱（DN）清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="cc246-569">這個屬性指定了一或多個電話路由的上一頁連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="cc246-570">返回連結：<strong>連結識別碼 11033</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="cc246-571">這個屬性會對應到轉寄連結<strong>msRTCSIP-RouteUsageLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-572">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-573">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-574">msRTCSIP-PhoneRouteData （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-575">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-576">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-577">msRTCSIP-PhoneRouteName （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-578">這個單一值 UNICODE 字串屬性會指定電話路線的易記名稱，所以系統管理員可以輕鬆地參考它。</span><span class="sxs-lookup"><span data-stu-id="cc246-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="cc246-579">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-580">msRTCSIP-PhoneUsageData （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-581">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-582">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-583">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-584">msRTCSIP-PolicyContent （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-585">這個屬性是單一值的 Unicode 字串。</span><span class="sxs-lookup"><span data-stu-id="cc246-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="cc246-586">這個字串屬性包含 XML 格式的原則定義。</span><span class="sxs-lookup"><span data-stu-id="cc246-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="cc246-587">XML 架構定義在不同的原則類型中是通用的，只有每個原則類型的設定都是不同的。</span><span class="sxs-lookup"><span data-stu-id="cc246-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="cc246-588">XML 架構定義（XSD）的定義如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="cc246-589">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-590">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-591">msRTCSIP-PolicyData （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-592">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-593">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-594">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-595">msRTCSIP-PolicyType （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-596">這個單一值的 Unicode 字串屬性包含原則類型。</span><span class="sxs-lookup"><span data-stu-id="cc246-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="cc246-597">有效的原則類型如下：</span><span class="sxs-lookup"><span data-stu-id="cc246-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-598">要求</span><span class="sxs-lookup"><span data-stu-id="cc246-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="cc246-599">$</span><span class="sxs-lookup"><span data-stu-id="cc246-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-600">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-601">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="cc246-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="cc246-603">這個屬性會指定回到電腦所屬之池的連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="cc246-604">無論電腦執行的是標準版或企業版的 Lync Server，都要設定此屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="cc246-605">這個屬性標示為供全域編目複製。</span><span class="sxs-lookup"><span data-stu-id="cc246-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="cc246-606">有效值為 pool 的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cc246-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="cc246-607">轉寄連結：<strong>連結識別碼 11022</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="cc246-608">與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-FrontEndServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-609">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="cc246-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="cc246-611">這是一個多重值屬性，其中包含與 MCU 工廠相關聯之 pool 的辨別名稱（DN）清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="cc246-612">返回連結：<strong>連結識別碼 11025</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="cc246-613">此返回連結的相對前連結是<strong>msRTCSIP-MCUFactoryPath</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-614">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="cc246-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="cc246-616">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-617">即時通訊伺服器2005中的新功能（含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="cc246-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="cc246-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="cc246-619">這個屬性會指定管理主控台所顯示之池的任意名稱。</span><span class="sxs-lookup"><span data-stu-id="cc246-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="cc246-620">系統管理員可以變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="cc246-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="cc246-621">有效的值是代表某個池名稱的字串。</span><span class="sxs-lookup"><span data-stu-id="cc246-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="cc246-622">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="cc246-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="cc246-624">這個屬性是單一值的字串值。</span><span class="sxs-lookup"><span data-stu-id="cc246-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="cc246-625">此屬性的值（如果有的話）代表池的網域 FQDN （如果系統管理員想要使用不符合在其中建立頂層端池之 Active Directory 網域結構的 FQDN）來建立該前端池（例如，SIP從 Domain Name System （DNS）命名空間中移除命名空間。</span><span class="sxs-lookup"><span data-stu-id="cc246-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="cc246-626">我們建議您將前端池網域 FQDN 對應至功能變數名稱部分，將其放在該池所在的 Active Directory 網域中。</span><span class="sxs-lookup"><span data-stu-id="cc246-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="cc246-627">因此，如果此屬性中沒有值，則 [前端] 池 FQDN 將預設為 Active Directory 功能變數名稱結構（由<strong>dnsHostName</strong>屬性工作表示）。</span><span class="sxs-lookup"><span data-stu-id="cc246-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="cc246-628">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="cc246-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="cc246-630">多值清單，其中列出與某個池關聯的所有 Lync Server、企業版伺服器的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cc246-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="cc246-631">此整數類型的這個屬性會定義該池是否具備立即訊息（IM）與目前狀態及會議。</span><span class="sxs-lookup"><span data-stu-id="cc246-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="cc246-632">可能的有效值類型如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-633">未定義： IM 和目前狀態服務（即時通訊伺服器2005和2003）</span><span class="sxs-lookup"><span data-stu-id="cc246-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="cc246-634">1： IM 和目前狀態服務（Lync Server）</span><span class="sxs-lookup"><span data-stu-id="cc246-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="cc246-635">2： IM 和目前狀態與會議服務（Lync Server）</span><span class="sxs-lookup"><span data-stu-id="cc246-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-636">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="cc246-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="cc246-638">這個屬性指定伺服器池是否正在執行標準版 server 或 Enterprise Edition 伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc246-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="cc246-639">這個屬性是 integer 類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="cc246-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="cc246-640">每個選項都是由一個位來表示。</span><span class="sxs-lookup"><span data-stu-id="cc246-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="cc246-641">有效值（以及相關聯的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-642">1：標準版伺服器、主機使用者（位位置0）</span><span class="sxs-lookup"><span data-stu-id="cc246-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="cc246-643">2：企業版 server、主機使用者（位位置1）</span><span class="sxs-lookup"><span data-stu-id="cc246-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="cc246-644">4：標準版伺服器、主機應用程式（位位置2）</span><span class="sxs-lookup"><span data-stu-id="cc246-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="cc246-645">8：企業版 server、主機應用程式（位位置3）</span><span class="sxs-lookup"><span data-stu-id="cc246-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="cc246-646">因為 Lync Server 不支援僅限託管應用程式的池，所以唯一有效的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-647">5：標準版 server、主機使用者和應用程式（bit 位置0和2）</span><span class="sxs-lookup"><span data-stu-id="cc246-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="cc246-648">10：企業版 server、主機使用者和應用程式（bit 位置1和3）</span><span class="sxs-lookup"><span data-stu-id="cc246-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-649">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="cc246-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="cc246-651">這個屬性會定義池子版本。</span><span class="sxs-lookup"><span data-stu-id="cc246-651">This attribute defines the pool version.</span></span> <span data-ttu-id="cc246-652">它是每個主要產品發行增加的整數類型。</span><span class="sxs-lookup"><span data-stu-id="cc246-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="cc246-653">可能的有效值類型如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-654">0：即時通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="cc246-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="cc246-655">1：即時通訊伺服器2005</span><span class="sxs-lookup"><span data-stu-id="cc246-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="cc246-656">2：即時通訊伺服器2005與 SP1</span><span class="sxs-lookup"><span data-stu-id="cc246-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="cc246-657">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="cc246-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="cc246-658">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cc246-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="cc246-659">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cc246-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-660">即時通訊伺服器2005（含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="cc246-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="cc246-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="cc246-662">這個屬性包含定義目前狀態設定的選項和標誌。</span><span class="sxs-lookup"><span data-stu-id="cc246-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="cc246-663">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="cc246-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="cc246-665">這個屬性包含目前狀態原則物件的 DN。</span><span class="sxs-lookup"><span data-stu-id="cc246-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="cc246-666">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="cc246-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="cc246-668">此屬性可讓使用者或連絡人進行 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="cc246-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="cc246-669">因為在中央目錄林拓撲中，連絡人物件（而非使用者物件）是 SIP 啟用的，所以會將它加入連絡人類別。</span><span class="sxs-lookup"><span data-stu-id="cc246-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="cc246-670">有效值為使用者所駐留之標準版 server 或 Enterprise Edition 前端池的 DN。</span><span class="sxs-lookup"><span data-stu-id="cc246-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="cc246-671">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="cc246-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="cc246-673">這個屬性包含指定使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="cc246-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="cc246-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="cc246-675">這個屬性包含專用線路裝置的裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="cc246-676">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-677">msRTCSIP 路由</span><span class="sxs-lookup"><span data-stu-id="cc246-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="cc246-678">這個屬性是一個布林值屬性，用來判斷 Lync Server 是否有授權使用其 GRUU 位址路由至此服務。</span><span class="sxs-lookup"><span data-stu-id="cc246-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="cc246-679">如果此值設定為<strong>TRUE</strong>，則 Lync Server 有權路由至此服務。</span><span class="sxs-lookup"><span data-stu-id="cc246-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="cc246-680">如果此值設定為<strong>FALSE</strong>，則 Lync Server 無權路由至此服務。</span><span class="sxs-lookup"><span data-stu-id="cc246-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="cc246-681">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-682">msRTCSIP-RouteUsageAttribute （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-683">這個單一值的 UNICODE 字串屬性會定義一個限定手機路線用法的屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="cc246-684">手機路線的選取是根據兩個元素來決定：指派給手機路線的使用方式屬性，以及來電者的允許原則使用屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="cc246-685">已選取與本機號碼的使用方式屬性相符的第一個電話路線。</span><span class="sxs-lookup"><span data-stu-id="cc246-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="cc246-686">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-687">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-688">msRTCSIP-RouteUsageLinks （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-689">這個多重值的辨別名稱（DN）屬性包含路由使用的可分辨名稱清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="cc246-690">轉寄連結：<strong>連結識別碼 11032</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="cc246-691">這個屬性是相對應的 back 連結<strong>msRTCSIP-PhoneRouteBL</strong>的轉寄連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-692">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="cc246-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="cc246-694">這個屬性包含指向您針對此 MCU 或受信任的服務所傳送之所有 SIP 流量必須經過的該池的 DN。</span><span class="sxs-lookup"><span data-stu-id="cc246-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="cc246-695">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-696">msRTCSIP-RuleName （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-697">這個單一值的 UNICODE 字串屬性會指定正常化規則的易記名稱，所以系統管理員可以輕鬆地參考它。</span><span class="sxs-lookup"><span data-stu-id="cc246-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="cc246-698">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-699">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="cc246-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="cc246-701">這個屬性代表目前部署在組織中的架構版本。</span><span class="sxs-lookup"><span data-stu-id="cc246-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-702">msRTCSIP-SearchMaxRequests （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-703">這個屬性會限制使用者使用 Communicator 搜尋連絡人時，從目錄搜尋傳回的搜尋結果數目。</span><span class="sxs-lookup"><span data-stu-id="cc246-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="cc246-704">這個屬性會覆寫用戶端提供的值。</span><span class="sxs-lookup"><span data-stu-id="cc246-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="cc246-705">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-706">msRTCSIP-SearchMaxResults （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-707">這個屬性會限制傳回的搜尋要求數目。</span><span class="sxs-lookup"><span data-stu-id="cc246-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="cc246-708">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="cc246-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="cc246-710">這個多重值屬性是一個包含辨識名稱（DN）清單的返回連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="cc246-711">這些 DNs 指向一個 pool 或<strong>TrustedService</strong>物件。</span><span class="sxs-lookup"><span data-stu-id="cc246-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="cc246-712">這個屬性會對應到轉寄連結<strong>msRTCSIP-TrustedServiceLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-713">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="cc246-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="cc246-715">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-716">msRTCSIP-ServerReferenceBL （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-717">這個多重值屬性包含辨識名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="cc246-718">這些辨識名稱會傳回參照可指派預設位置設定檔之其他伺服器物件的連結。</span><span class="sxs-lookup"><span data-stu-id="cc246-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="cc246-719">返回連結：<strong>連結識別碼 11037</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="cc246-720">此返回連結的相對前連結是<strong>msRTCSIP-DefaultLocationProfileLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="cc246-721">這個返回連結屬性只會參照池和轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc246-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="cc246-722">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-723">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="cc246-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="cc246-725">這個屬性會定義伺服器的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="cc246-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="cc246-726">此版本號碼適用于所有伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="cc246-726">This version number applies to all server roles.</span></span> <span data-ttu-id="cc246-727">它是一種 monotonously 增加的整數，會隨著每個正式產品發行而增加。</span><span class="sxs-lookup"><span data-stu-id="cc246-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="cc246-728">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="cc246-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-729">未定義：即時通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="cc246-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="cc246-730">                 [即時通訊伺服器] 2005</span><span class="sxs-lookup"><span data-stu-id="cc246-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="cc246-731">                 使用 SP1 進行即時通訊伺服器2005</span><span class="sxs-lookup"><span data-stu-id="cc246-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="cc246-732">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="cc246-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="cc246-733">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cc246-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="cc246-734">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cc246-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="cc246-735">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc246-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-736">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="cc246-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="cc246-738">整數類型的這個單值屬性會指定<strong>SourceObjectDN</strong>指向的物件類型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-739">null |0x00000001：代表不同林中的 Windows NT 伺服器主體使用者物件</span><span class="sxs-lookup"><span data-stu-id="cc246-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="cc246-740">下列屬性代表通訊群組延伸的不同樹林中的群組類型：</span><span class="sxs-lookup"><span data-stu-id="cc246-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-741">0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="cc246-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="cc246-742">0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="cc246-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="cc246-743">0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="cc246-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="cc246-744">0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="cc246-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="cc246-745">0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="cc246-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="cc246-746">0x90000000：代表來自同一個目錄林或不同林中的自動助理或訂閱者存取物件</span><span class="sxs-lookup"><span data-stu-id="cc246-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="cc246-747">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-748">msRTCSIP-SubscriptionAuthRequired （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-749">即時通訊伺服器2003中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="cc246-750">在即時通訊伺服器2005中過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="cc246-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="cc246-752">這個屬性可讓您將使用者或連絡人物件從一個 Lync 伺服器池移至另一個。</span><span class="sxs-lookup"><span data-stu-id="cc246-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="cc246-753">這個屬性會新增至 contact 類別，因為在中央目錄林拓撲中，連絡人物件（而非使用者物件）是 SIP 啟用的。</span><span class="sxs-lookup"><span data-stu-id="cc246-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="cc246-754">有效值是要將使用者移至其中的目的地標準版伺服器或前端池之 DN。</span><span class="sxs-lookup"><span data-stu-id="cc246-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="cc246-755">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-756">msRTCSIP-TargetPhoneNumber （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-757">這個單值字串屬性包含電話號碼模式或範圍，以路由至在<strong>msRTCSIP-閘道</strong>中定義的指定閘道。</span><span class="sxs-lookup"><span data-stu-id="cc246-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-758">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="cc246-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="cc246-760">這個屬性會儲存 Lync Server 使用者之目標原則的名稱/值對。</span><span class="sxs-lookup"><span data-stu-id="cc246-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="cc246-761">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="cc246-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="cc246-763">這個屬性會儲存租使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="cc246-764">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-765">msRTCSIP-翻譯（已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-766">這個屬性是由 Lync Server 的語音功能所使用，而且包含要在撥打電話號碼上套用的翻譯字串（如果找到相符專案）。</span><span class="sxs-lookup"><span data-stu-id="cc246-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="cc246-767">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="cc246-768">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="cc246-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="cc246-770">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-771">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="cc246-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="cc246-773">這個屬性是包含 MCU FQDN 的字串值。</span><span class="sxs-lookup"><span data-stu-id="cc246-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="cc246-774">這是單值屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-774">This is a single-valued attribute.</span></span> <span data-ttu-id="cc246-775">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="cc246-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="cc246-776">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="cc246-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="cc246-778">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-779">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="cc246-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="cc246-781">這個屬性是一個字串值，其中包含執行 Proxy 伺服器之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cc246-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="cc246-782">這個屬性是單一值。</span><span class="sxs-lookup"><span data-stu-id="cc246-782">This attribute is single-valued.</span></span> <span data-ttu-id="cc246-783">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="cc246-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="cc246-784">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="cc246-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="cc246-786">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="cc246-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="cc246-788">這個屬性是一個代表信任伺服器 FQDN 的單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="cc246-789">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="cc246-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="cc246-791">這個屬性會指定可信伺服器清單中伺服器的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="cc246-792">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="cc246-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-793">Null：即時通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="cc246-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="cc246-794">2：即時通訊伺服器2005</span><span class="sxs-lookup"><span data-stu-id="cc246-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="cc246-795">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="cc246-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="cc246-796">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="cc246-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="cc246-797">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cc246-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="cc246-798">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc246-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-799">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="cc246-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="cc246-801">這個屬性會定義受信任服務啟用的選項。</span><span class="sxs-lookup"><span data-stu-id="cc246-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="cc246-802">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="cc246-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="cc246-804">這個多重值屬性包含參照受信任的服務物件（例如媒體轉送驗證服務）的辨識名稱（DN）清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="cc246-805">媒體轉送驗證服務（在執行 A/V 會議服務的邊緣伺服器上實際 collocated）必須與一個池建立關聯，才能支援遠端使用者的音訊案例。</span><span class="sxs-lookup"><span data-stu-id="cc246-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="cc246-806">與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-ServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-807">整合通訊</span><span class="sxs-lookup"><span data-stu-id="cc246-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="cc246-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="cc246-809">這個屬性是一個整數，定義用來連接此 GRUU 服務的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="cc246-810">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="cc246-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="cc246-812">這個屬性是一個定義其所代表之 GRUU 服務類型的字串值。</span><span class="sxs-lookup"><span data-stu-id="cc246-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="cc246-813">有效的 GRUU 服務類型如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="cc246-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="cc246-815">關</span><span class="sxs-lookup"><span data-stu-id="cc246-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="cc246-816">媒體轉送驗證服務（MRAS）</span><span class="sxs-lookup"><span data-stu-id="cc246-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="cc246-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="cc246-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="cc246-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="cc246-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-819">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="cc246-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="cc246-821">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-822">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="cc246-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="cc246-824">這個屬性是一個字串值，其中包含執行 Lync Server Web 服務的 IIS FQDN。</span><span class="sxs-lookup"><span data-stu-id="cc246-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="cc246-825">這是單值屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-825">This is a single-valued attribute.</span></span> <span data-ttu-id="cc246-826">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="cc246-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="cc246-827">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-828">msRTCSIP-UCFlags （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-829">這個屬性定義不同的 UC 選項，這些選項會針對所有使用者或連絡人物件全域啟用。</span><span class="sxs-lookup"><span data-stu-id="cc246-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="cc246-830">這個屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="cc246-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="cc246-831">每個選項都是由一個位所代表。</span><span class="sxs-lookup"><span data-stu-id="cc246-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="cc246-832">可能的有效值（以及相關聯的位位置）如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-833">4： UsePerUserUCPolicy （bit 位置2）</span><span class="sxs-lookup"><span data-stu-id="cc246-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="cc246-834">如果設定了這個位數，UC 原則就會定義為 [每位使用者]。</span><span class="sxs-lookup"><span data-stu-id="cc246-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="cc246-835">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-836">msRTCSIP-UCPolicy （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-837">這個單一值屬性包含管理員已指派給此使用者的 UC 原則的辨識名稱（DN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="cc246-838">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-839">msRTCSIP-UserDomainList （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="cc246-840">這個屬性提供林中所有主機擁有 SIP 的使用者的網域清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="cc246-841">預設值為空白清單，表示林中的所有網域都已啟用 SIP。</span><span class="sxs-lookup"><span data-stu-id="cc246-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="cc246-842">有效值為多個字串，代表個別網域的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="cc246-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="cc246-843">即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="cc246-844">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="cc246-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="cc246-846">這個屬性會判斷使用者目前是否已啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="cc246-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="cc246-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="cc246-848">這個多重值屬性包含名稱 = 值格式&quot;的名稱/值對清單。&quot;這個屬性標示為供全域編目複製。</span><span class="sxs-lookup"><span data-stu-id="cc246-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="cc246-849">即時通訊伺服器2005中的新功能（含 SP1）。</span><span class="sxs-lookup"><span data-stu-id="cc246-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="cc246-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="cc246-851">這個屬性包含指向位置設定檔物件的辨別名稱（DN）。</span><span class="sxs-lookup"><span data-stu-id="cc246-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="cc246-852">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="cc246-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="cc246-854">這個屬性會儲存使用者原則的名稱/值對。</span><span class="sxs-lookup"><span data-stu-id="cc246-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="cc246-855">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="cc246-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="cc246-857">這是包含辨識名稱清單的多重值屬性，二進位（DN_WITH_BINARY）指向不同類型的全域使用者原則。</span><span class="sxs-lookup"><span data-stu-id="cc246-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="cc246-858">二進位部分指出 DN 部分指向的原則類型。</span><span class="sxs-lookup"><span data-stu-id="cc246-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="cc246-859">有效的二進位值如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc246-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-860">0x00000001：會議原則</span><span class="sxs-lookup"><span data-stu-id="cc246-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="cc246-861">0x00000002： UC 原則</span><span class="sxs-lookup"><span data-stu-id="cc246-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="cc246-862">0x00000005：目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="cc246-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-863">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="cc246-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="cc246-865">這是 SIP 路由群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="cc246-866">相同群組中的使用者會註冊到相同的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc246-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="cc246-867">Lync Server 2013 的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="cc246-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="cc246-869">這是多重值屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="cc246-870">這個屬性已保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="cc246-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="cc246-871">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="cc246-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="cc246-873">這個單一值屬性會指向網頁元件所屬的 pool 或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc246-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="cc246-874">轉寄連結：<strong>連結識別碼 11028</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="cc246-875">與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-WebComponentsServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-876">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="cc246-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="cc246-878">這個屬性是多值的辨識名稱清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="cc246-879">這個屬性包含與此 pool 關聯的所有 Web 服務器清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="cc246-880">返回連結：<strong>連結識別碼 11029</strong></span><span class="sxs-lookup"><span data-stu-id="cc246-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="cc246-881">此返回連結的相對前連結是<strong>msRTCSIP-WebComponentsPoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="cc246-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="cc246-882">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-883">msRTCSIP-WMIInstanceId （已過時）</span><span class="sxs-lookup"><span data-stu-id="cc246-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="cc246-884">即時通訊伺服器2003中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="cc246-885">在即時通訊伺服器2005中過時。</span><span class="sxs-lookup"><span data-stu-id="cc246-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="cc246-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="cc246-887">[電話語音] 會使用這個現有的 Active Directory 屬性來指定手機的備用 TCP/IP 地址清單。</span><span class="sxs-lookup"><span data-stu-id="cc246-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="cc246-888">Windows Server 2008 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="cc246-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="cc246-890">在 Lync Server 的語音元件中，只有連絡人物件，才會使用這個現有的 Active Directory 屬性，目的是將呼叫路由到統一訊息自動助理和訂閱者存取號碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="cc246-891">無條件來電轉接位址會儲存在這個多重值屬性中。</span><span class="sxs-lookup"><span data-stu-id="cc246-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="cc246-892">這個帳戶是針對自動助理和訂閱者存取的特定用途而建立。</span><span class="sxs-lookup"><span data-stu-id="cc246-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="cc246-893">系統管理員不應該修改這個帳戶的屬性。</span><span class="sxs-lookup"><span data-stu-id="cc246-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="cc246-894">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc246-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="cc246-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="cc246-896">這個現有的 Active Directory 多重值屬性是 Windows 2000 中所引進之基本 Active Directory 架構的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc246-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="cc246-897">這個屬性包含使用者電子郵件的各種 X400、X500 及 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="cc246-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="cc246-898">在 [即時通訊伺服器2003及更新版本] 中，使用者的 SIP URI 會新增至此清單&quot;（使用&quot; [SIP：] 標記）。</span><span class="sxs-lookup"><span data-stu-id="cc246-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="cc246-899">下列應用程式會從這個屬性搜尋使用者的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="cc246-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc246-900">Microsoft Office Outlook 2003 訊息與共同作業用戶端</span><span class="sxs-lookup"><span data-stu-id="cc246-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="cc246-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="cc246-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cc246-902">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc246-903">Telephonenumber 相同</span><span class="sxs-lookup"><span data-stu-id="cc246-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="cc246-904">這個現有的 Active Directory 屬性包含使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="cc246-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="cc246-905">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="cc246-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

