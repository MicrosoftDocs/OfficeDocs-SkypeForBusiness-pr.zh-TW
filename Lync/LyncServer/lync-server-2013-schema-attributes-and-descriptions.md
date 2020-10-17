---
title: Lync Server 2013：架構屬性和描述
description: Lync Server 2013：架構屬性和描述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557189"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="66579-103">Lync Server 2013 中的架構屬性和描述</span><span class="sxs-lookup"><span data-stu-id="66579-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66579-104">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="66579-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="66579-105">本節說明 Lync Server 2013 所使用的所有架構屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="66579-106">如需與屬性相關聯的類別，請參閱 [在 Lync Server 2013 中依類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="66579-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="66579-107">如需 Lync Server 2013 中新的類別和屬性清單，請參閱 [Lync server 2013 中的架構變更](lync-server-2013-schema-changes-in-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="66579-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="66579-108">連結成對的屬性會指定為正向連結或反向連結。</span><span class="sxs-lookup"><span data-stu-id="66579-108">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="66579-109">參照至另一個物件的屬性是轉寄連結;參照至第一個物件的另一個物件的屬性是 back 連結。</span><span class="sxs-lookup"><span data-stu-id="66579-109">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="66579-110">轉寄連結是可更新的，而 back 連結是唯讀的。</span><span class="sxs-lookup"><span data-stu-id="66579-110">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="66579-111">有些屬性具有位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="66579-111">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="66579-112">針對這些屬性，每個設定都是以位表示，顯示的十進位值代表位位置。</span><span class="sxs-lookup"><span data-stu-id="66579-112">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="66579-113">位位置以位0開始。</span><span class="sxs-lookup"><span data-stu-id="66579-113">Bit positions start with bit 0.</span></span> <span data-ttu-id="66579-114">例如，1 (二進位) 為 bit 0 設定，而 10000 (二進位) 是位4集。</span><span class="sxs-lookup"><span data-stu-id="66579-114">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="66579-115">每個位代表一個屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-115">Each bit represents a property.</span></span> <span data-ttu-id="66579-116">以下是一些範例：</span><span class="sxs-lookup"><span data-stu-id="66579-116">The following are some examples:</span></span>

  - <span data-ttu-id="66579-117">10000 (二進位) 具有十進位值 16 (，也就是設定) 的位4。</span><span class="sxs-lookup"><span data-stu-id="66579-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="66579-118">100000000 (二進位) 的十進位值為 256 (也就是設定) 的位8。</span><span class="sxs-lookup"><span data-stu-id="66579-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="66579-119">1100 (二進位) 的十進位值為 12 (，也就是設定位2和 3;) 啟用兩個位代表的屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="66579-120">1111000001 (二進位) 具有十進位值 961 (也就是設定位0、6、7、8和9。這兩個位的屬性都已) 啟用。</span><span class="sxs-lookup"><span data-stu-id="66579-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="66579-121">Lync Server 2013 的架構屬性</span><span class="sxs-lookup"><span data-stu-id="66579-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66579-122">屬性</span><span class="sxs-lookup"><span data-stu-id="66579-122">Attribute</span></span></th>
<th><span data-ttu-id="66579-123">描述</span><span class="sxs-lookup"><span data-stu-id="66579-123">Description</span></span></th>
<th><span data-ttu-id="66579-124">註解</span><span class="sxs-lookup"><span data-stu-id="66579-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66579-125">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="66579-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="66579-126">現在與 <strong>MsRTCSIP 集</strong> 區及 <strong>msRTCSIP MonitoringServer</strong> 類別相關聯之 Active Directory 網域服務中的現有屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="66579-127">此屬性會指定集區或監控伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="66579-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="66579-128">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="66579-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="66579-129">Microsoft Office Live 通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-130">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="66579-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="66579-131">此屬性包含另一個樹系中物件的辨識名稱 (DN) 的字串標記法，該物件會對應至此物件。</span><span class="sxs-lookup"><span data-stu-id="66579-131">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="66579-132">此屬性用於通訊群組擴充和自動出勤。</span><span class="sxs-lookup"><span data-stu-id="66579-132">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="66579-133">此屬性是在 Windows Server 2003 R2 的預設 Active Directory 架構中定義的。</span><span class="sxs-lookup"><span data-stu-id="66579-133">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="66579-134">為了避免需要將 AD DS 升級為 Windows Server 2003 R2，Active Directory 架構準備會以此屬性定義延伸 Windows Server 2003 架構。</span><span class="sxs-lookup"><span data-stu-id="66579-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="66579-135">Microsoft Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-136">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="66579-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="66579-137">此多重值屬性包含語音信箱設定。</span><span class="sxs-lookup"><span data-stu-id="66579-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="66579-138">此屬性與 Exchange 整合通訊 (UM) 共用。</span><span class="sxs-lookup"><span data-stu-id="66579-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="66579-139">Microsoft Lync Server 2010 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="66579-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="66579-141">此多重值屬性包含適用于使用者之保留原則的識別碼。</span><span class="sxs-lookup"><span data-stu-id="66579-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="66579-142">保留原則會在保留期間保留使用者的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="66579-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="66579-143">此屬性與 Exchange 2013 共用。</span><span class="sxs-lookup"><span data-stu-id="66579-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="66579-144">Lync Server 2013 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-145">msRTCSIP AcpInfo</span><span class="sxs-lookup"><span data-stu-id="66579-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="66579-146">此屬性會儲存使用者的音訊會議提供者資訊。</span><span class="sxs-lookup"><span data-stu-id="66579-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="66579-147">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-148">msRTCSIP ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="66579-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="66579-149">此屬性指向應用程式連絡人的信任服務專案。</span><span class="sxs-lookup"><span data-stu-id="66579-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="66579-150">Microsoft Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-151">msRTCSIP ApplicationList</span><span class="sxs-lookup"><span data-stu-id="66579-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="66579-152">此屬性包含應用程式伺服器上的主控應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="66579-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="66579-153">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-154">msRTCSIP ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="66579-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="66579-155">此屬性會指定應用程式連絡人的選項。</span><span class="sxs-lookup"><span data-stu-id="66579-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="66579-156">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-157">msRTCSIP ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="66579-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="66579-158">此屬性包含應用程式連絡人的主要語言。</span><span class="sxs-lookup"><span data-stu-id="66579-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="66579-159">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-160">msRTCSIP ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="66579-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="66579-161">此多重值屬性包含應用程式連絡人的次要語言。</span><span class="sxs-lookup"><span data-stu-id="66579-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="66579-162">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-163">msRTCSIP ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="66579-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="66579-164">此屬性包含隸屬于此集區的應用程式伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="66579-164">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="66579-165">此反向連結屬性的對應正向連結是 <strong>msRTCSIP-ApplicationServerPoolLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-165">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-166">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-167">msRTCSIP ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="66579-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="66579-168">此屬性指向此應用程式伺服器所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="66579-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="66579-169">這是轉寄連結。</span><span class="sxs-lookup"><span data-stu-id="66579-169">This is the forward link.</span></span> <span data-ttu-id="66579-170">對應的 [反向] 連結是 <strong>msRTCSIP-ApplicationServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-171">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-172">msRTCSIP-ArchiveDefault (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-173">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-174">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-175">msRTCSIP-ArchiveDefaultFlags (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-176">此屬性指定樹系界限內的全域預設值，以封存所有使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="66579-176">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="66579-177">這是由封存代理程式層強制執行。</span><span class="sxs-lookup"><span data-stu-id="66579-177">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="66579-178">此屬性的值範圍如下：</span><span class="sxs-lookup"><span data-stu-id="66579-178">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-179"><strong>TRUE</strong>：封存所有使用者</span><span class="sxs-lookup"><span data-stu-id="66579-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="66579-180"><strong>FALSE</strong>：不封存所有使用者</span><span class="sxs-lookup"><span data-stu-id="66579-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="66579-181">此屬性會在樹系界限內，全域控制如何封存內部網路中的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="66579-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="66579-182"><strong>即時通訊伺服器2005行為 (現已撤銷) </strong></span><span class="sxs-lookup"><span data-stu-id="66579-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="66579-183">此屬性的值範圍如下：</span><span class="sxs-lookup"><span data-stu-id="66579-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-184">0：封存郵件本文 [位 0]</span><span class="sxs-lookup"><span data-stu-id="66579-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="66579-185">1：不要封存郵件本文 [位 0]</span><span class="sxs-lookup"><span data-stu-id="66579-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="66579-186"><strong>Office 通訊伺服器2007行為</strong></span><span class="sxs-lookup"><span data-stu-id="66579-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="66579-187">此屬性的值範圍如下：</span><span class="sxs-lookup"><span data-stu-id="66579-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-188">0： ArchiveFederationDefaultWithoutBody (撤銷) </span><span class="sxs-lookup"><span data-stu-id="66579-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="66579-189">1-2： ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="66579-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="66579-190">3-4： ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="66579-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="66579-191">5： RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="66579-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="66579-192">6： RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="66579-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="66579-193">7： RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="66579-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="66579-194">8： RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="66579-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="66579-195">9： RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="66579-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="66579-196">10： RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="66579-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="66579-197">11： RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="66579-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="66579-198">12： RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="66579-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="66579-199">13： RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="66579-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="66579-200">14： RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="66579-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="66579-201">15： RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="66579-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="66579-202">16： RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="66579-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-203">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-204">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-205">msRTCSIP-ArchiveFederationDefault (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-206">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-207">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-208">msRTCSIP-ArchiveFederationDefaultFlags (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-209">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-210">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-211">msRTCSIP ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="66579-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="66579-212">此屬性是一種整數，用來控制是否要封存單一使用者的通訊的位欄位。</span><span class="sxs-lookup"><span data-stu-id="66579-212">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="66579-213">此控制項是由封存代理程式層強制執行。</span><span class="sxs-lookup"><span data-stu-id="66579-213">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="66579-214">它會標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="66579-214">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="66579-215">此屬性的範圍是單一使用者或連絡人特有的。</span><span class="sxs-lookup"><span data-stu-id="66579-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="66579-216">在 Lync Server 中)  (和關聯位位置的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="66579-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-217">0：不封存 (未設定任何位) </span><span class="sxs-lookup"><span data-stu-id="66579-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="66579-218">1：已撤銷 (位位置 0) </span><span class="sxs-lookup"><span data-stu-id="66579-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="66579-219">2：已撤銷 (位位置 1) </span><span class="sxs-lookup"><span data-stu-id="66579-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="66579-220">4：封存內部通訊 (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="66579-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="66579-221">8：封存同盟通訊 (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="66579-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="66579-222">Live 迅 Server 2005 中先前有效的值如下：</span><span class="sxs-lookup"><span data-stu-id="66579-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-223">0：使用依下列優先順序 <strong>msRTCSIP-ArchiveDefault</strong> 和 <strong>msRTCSIP-ArchiveFederation</strong> 所定義的預設值：</span><span class="sxs-lookup"><span data-stu-id="66579-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-224">1：封存</span><span class="sxs-lookup"><span data-stu-id="66579-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="66579-225">2：不要封存</span><span class="sxs-lookup"><span data-stu-id="66579-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="66579-226">3：不含郵件內文的封存</span><span class="sxs-lookup"><span data-stu-id="66579-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="66579-227">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-228">msRTCSIP-ArchivingServerData (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-229">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-230">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-231">msRTCSIP-ArchivingServerVersion (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-232">此屬性會定義封存服務的版本。</span><span class="sxs-lookup"><span data-stu-id="66579-232">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="66579-233">此屬性是隨每個官方產品發行增加的 monotonously 增加整數類型。</span><span class="sxs-lookup"><span data-stu-id="66579-233">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="66579-234">可能的有效值為：</span><span class="sxs-lookup"><span data-stu-id="66579-234">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-235">未定義： Live 通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="66579-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="66579-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="66579-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="66579-237">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="66579-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="66579-238">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="66579-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="66579-239">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="66579-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-240">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-241">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-242">msRTCSIP BackEndServer</span><span class="sxs-lookup"><span data-stu-id="66579-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="66579-243">此屬性指定集區後端伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="66579-243">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="66579-244">因為每個集區只能有一個後端伺服器，所以這是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-244">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="66579-245">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="66579-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="66579-246">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-247">msRTCSIP ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="66579-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="66579-248">此屬性包含主控會議目錄之集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="66579-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="66579-249">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-250">msRTCSIP ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="66579-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="66579-251">此屬性包含會議目錄的識別碼。</span><span class="sxs-lookup"><span data-stu-id="66579-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="66579-252">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-253">msRTCSIP ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="66579-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="66579-254">此屬性包含會議目錄移動所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="66579-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="66579-255">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-256">msRTCSIP-預設值</span><span class="sxs-lookup"><span data-stu-id="66579-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="66579-257">這個 Boolean 屬性定義電話使用方式是否為預設使用量。</span><span class="sxs-lookup"><span data-stu-id="66579-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="66579-258">如果此屬性設定為 <strong>TRUE</strong>，則系統會使用電話的預設值，且無法由系統管理員刪除。</span><span class="sxs-lookup"><span data-stu-id="66579-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="66579-259">如果此屬性設為 <strong>FALSE</strong>，則可刪除使用方式。</span><span class="sxs-lookup"><span data-stu-id="66579-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="66579-260">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-261">msRTCSIP DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="66579-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="66579-262">此屬性會識別組織外部使用者的 Communicator Web Access URL。</span><span class="sxs-lookup"><span data-stu-id="66579-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="66579-263">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-264">msRTCSIP DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="66579-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="66579-265">此屬性會識別組織內部使用者的 Communicator Web Access URL。</span><span class="sxs-lookup"><span data-stu-id="66579-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="66579-266">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-267">msRTCSIP-DefaultLocationProfileLink (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-268">這個單一值屬性包含指派給它的位置設定檔類別物件 (DN) 的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="66579-269">轉寄連結： <strong>連結 ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="66579-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="66579-270">對應的反向連結 <strong>msRTCSIP-ServerReferenceBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-271">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-272">msRTCSIP-DefaultPolicy (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-273">這個布林值屬性指定原則是否為預設原則。</span><span class="sxs-lookup"><span data-stu-id="66579-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="66579-274">原則是設定為 <strong>TRUE</strong>時的預設原則。</span><span class="sxs-lookup"><span data-stu-id="66579-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-275">Office 通訊伺服器2007的新增功能</span><span class="sxs-lookup"><span data-stu-id="66579-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="66579-276">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-277">msRTCSIP-DefaultRouteToEdgeProxy (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-278">此屬性指定執行 Access Edge service 之 Edge Server 的 FQDN （如果可以直接存取），或指定執行 Access Edge service 之伺服器集區的硬體負載平衡器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="66579-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="66579-279">如果執行 Access Edge service 的伺服器只能透過一或多個 Director 存取，則此屬性會指定 FQDN，並選擇性地指定 Director 或硬體負載平衡器服務 Director 集區的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="66579-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="66579-280">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="66579-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="66579-281">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-282">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-283">msRTCSIP-DefaultRouteToEdgeProxyPort (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-284">此屬性代表應該用來連線至執行 Access Edge service 之伺服器的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="66579-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="66579-285">有效的值是指定要使用的埠的整數值。</span><span class="sxs-lookup"><span data-stu-id="66579-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="66579-286">預設值為5061。</span><span class="sxs-lookup"><span data-stu-id="66579-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="66579-287">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-288">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-289">msRTCSIP-DefPresenceSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-290">此屬性代表預設的目前狀態訂閱超時期間。</span><span class="sxs-lookup"><span data-stu-id="66579-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="66579-291">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-292">msRTCSIP-DefRegistrationTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-293">此屬性代表預設的註冊超時視窗。</span><span class="sxs-lookup"><span data-stu-id="66579-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="66579-294">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-296">此屬性代表預設的漫遊資料訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="66579-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="66579-297">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-298">msRTCSIP DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="66579-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="66579-299">此屬性會用於分割的網域拓撲，並包含完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="66579-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="66579-300">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-301">msRTCSIP-Description (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-302">這個單一值的 UNICODE 字串屬性包含此電話路由或正常化規則的易記描述。</span><span class="sxs-lookup"><span data-stu-id="66579-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="66579-303">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-304">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-305">msRTCSIP DomainData</span><span class="sxs-lookup"><span data-stu-id="66579-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="66579-306">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-307">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="66579-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="66579-308">此屬性代表針對註冊機構所設定的網域。</span><span class="sxs-lookup"><span data-stu-id="66579-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-309">msRTCSIP EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="66579-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="66579-310">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-311">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-312">msRTCSIP EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="66579-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="66579-313">此屬性指定執行 Access Edge service 之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="66579-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="66579-314">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="66579-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="66579-315">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-316">msRTCSIP-EnableBestEffortNotify (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-317">此屬性會控制伺服器是否會產生最佳的努力，以回應用戶端的訂閱要求 (BENOTIFY) 要求，而不是通知要求。</span><span class="sxs-lookup"><span data-stu-id="66579-317">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="66579-318">BENOTIFY 是對訂閱通知握手的效能擴充擴充，伺服器會產生 BENOTIFY 要求，而不是一般通知要求。</span><span class="sxs-lookup"><span data-stu-id="66579-318">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="66579-319">效能好處是 BENOTIFY 要求不需要用戶端的 200 OK 回應，因為 NOTIFY 要求會執行。</span><span class="sxs-lookup"><span data-stu-id="66579-319">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="66579-320">有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="66579-321">即時通訊伺服器2003不支援 BENOTIFY 要求。</span><span class="sxs-lookup"><span data-stu-id="66579-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="66579-322">若要與使用 live 迅 Server 2005 和協力廠商伺服器上執行的即時通訊伺服器2003伺服器 API 撰寫的伺服器應用程式互動，可將其值設為 <STRONG>FALSE</STRONG>，以停用 BENOTIFY 要求。</span><span class="sxs-lookup"><span data-stu-id="66579-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="66579-323">BENOTIFY 目前不屬於 IETF (網際網路工程工作小組) SIP 標準化處理常式。</span><span class="sxs-lookup"><span data-stu-id="66579-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="66579-324">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-325">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-326">msRTCSIP-EnableFederation (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-327">此屬性是一種全域參數，由 IT 系統管理員用來設定是否允許使用者與其他組織的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="66579-327">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="66579-328">它可讓系統管理員覆寫個別使用者的 <strong>FederationEnabled</strong> 屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-328">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="66579-329">此屬性可用來協助保護內部網路免受來自公司的蠕蟲、病毒或目標攻擊可能造成的網際網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="66579-329">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="66579-330">有效值 (和相關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="66579-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-331">1：啟用公用 IM 連線 (位位置 0) </span><span class="sxs-lookup"><span data-stu-id="66579-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="66579-332">2：保留 (位位置 1) </span><span class="sxs-lookup"><span data-stu-id="66579-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="66579-333">4：保留 (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="66579-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="66579-334">8：保留 (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="66579-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="66579-335">16：已啟用遠端呼叫控制 [電話語音] (位位置 4) </span><span class="sxs-lookup"><span data-stu-id="66579-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="66579-336">64： AllowOrganizeMeetingWithAnonymousParticipants (允許使用者邀請匿名使用者加入會議 (位位置 6) </span><span class="sxs-lookup"><span data-stu-id="66579-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="66579-337">128： UCEnabled (為使用者啟用整合通訊)  (位位置 7) </span><span class="sxs-lookup"><span data-stu-id="66579-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="66579-338">256： EnabledForEnhancedPresence (啟用使用者的公用 IM 連線)  (位位置 8) </span><span class="sxs-lookup"><span data-stu-id="66579-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="66579-339">512： RemoteCallControlDualMode (位位置 9) </span><span class="sxs-lookup"><span data-stu-id="66579-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-340">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-341">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-342">msRTCSIP EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="66579-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="66579-343">此屬性會指出是否在指定的伺服器上載入企業服務。</span><span class="sxs-lookup"><span data-stu-id="66579-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-344">msRTCSIP ExtensionData</span><span class="sxs-lookup"><span data-stu-id="66579-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="66579-345">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-346">msRTCSIP ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="66579-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="66579-347">此屬性包含外部存取的撥號代碼。</span><span class="sxs-lookup"><span data-stu-id="66579-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="66579-348">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-349">msRTCSIP FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="66579-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="66579-350">此屬性控制是否為單一使用者啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="66579-350">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="66579-351">它會由企業服務層強制執行。</span><span class="sxs-lookup"><span data-stu-id="66579-351">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="66579-352">它會標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="66579-352">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="66579-353">有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-354">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-355">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="66579-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="66579-356">此屬性是與集區相關聯之所有 Enterprise Edition 伺服器的功能變數名稱的多重值清單。</span><span class="sxs-lookup"><span data-stu-id="66579-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="66579-357">反向連結： <strong>連結 ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="66579-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="66579-358">此反向連結的對應正向連結是 <strong>msRTCSIP-PoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-359">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-360">msRTCSIP-Gateways (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-361">這個多重值字串屬性包含每個閘道)  (的閘道和埠清單。</span><span class="sxs-lookup"><span data-stu-id="66579-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="66579-362">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-363">msRTCSIP-GlobalSettingsData (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-364">此屬性會儲存 [名稱：值] 配對。</span><span class="sxs-lookup"><span data-stu-id="66579-364">This attribute stores name:value pairs.</span></span> <span data-ttu-id="66579-365">已定義的 name： value 對適用于 <strong>允許輪詢顯示狀態</strong> 設定。</span><span class="sxs-lookup"><span data-stu-id="66579-365">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="66579-366">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-367">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="66579-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="66579-368">此屬性是群組的唯一識別碼，可用來群組通訊錄專案。</span><span class="sxs-lookup"><span data-stu-id="66579-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="66579-369">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-370">msRTCSIP-HomeServer (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-371">Live 通訊伺服器2003中的新增功能 (未使用) 。</span><span class="sxs-lookup"><span data-stu-id="66579-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="66579-372">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-373">msRTCSIP-HomeServerString (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-374">在即時通訊伺服器2003中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="66579-375">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-376">msRTCSIP-HomeUsers (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-377">Live 通訊伺服器2003中的新增功能 (未使用) 。</span><span class="sxs-lookup"><span data-stu-id="66579-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="66579-378">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-379">msRTCSIP InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="66579-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="66579-380">此屬性控制是否單一使用者啟用外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="66579-380">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="66579-381">它會由企業服務層強制執行。</span><span class="sxs-lookup"><span data-stu-id="66579-381">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="66579-382">它會標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="66579-382">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="66579-383">有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-384">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-385">msRTCSIP-IsMaster (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-386">即時通訊伺服器2003中的新功能</span><span class="sxs-lookup"><span data-stu-id="66579-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="66579-387">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-388">msRTCSIP 線</span><span class="sxs-lookup"><span data-stu-id="66579-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="66579-389">這個單一值屬性包含裝置識別碼 (使用者控制之電話的 SIP URI 或電話 URI，以供 Lync 用於電話語音) 使用。</span><span class="sxs-lookup"><span data-stu-id="66579-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="66579-390">此屬性標示為進行通用類別目錄複寫，而且已編制索引。</span><span class="sxs-lookup"><span data-stu-id="66579-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="66579-391">如果使用者已啟用 Enterprise Voice，則此屬性會儲存為 e.164 的使用者電話號碼版本（164）。</span><span class="sxs-lookup"><span data-stu-id="66579-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="66579-392">Microsoft Office Live 通訊伺服器2005與 SP1 的新增功能</span><span class="sxs-lookup"><span data-stu-id="66579-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-393">msRTCSIP LineServer</span><span class="sxs-lookup"><span data-stu-id="66579-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="66579-394">這個單一值屬性包含 CSTA-SIP 閘道伺服器的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="66579-394">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="66579-395">此屬性標示為通用類別目錄複寫，但沒有編制索引。</span><span class="sxs-lookup"><span data-stu-id="66579-395">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="66579-396">Microsoft Office Live 通訊伺服器2005與 SP1 的新增功能</span><span class="sxs-lookup"><span data-stu-id="66579-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-397">msRTCSIP-LocalNormalizationData (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-398">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-399">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-400">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-401">msRTCSIP-LocalNormalizationLinks (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-402">此多重值屬性包含本機正規化辨別名稱的清單，這些名稱是 (DN) 與此位置設定檔相關聯。</span><span class="sxs-lookup"><span data-stu-id="66579-402">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="66579-403">此屬性的類型是 DN 二進位。</span><span class="sxs-lookup"><span data-stu-id="66579-403">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="66579-404">位置設定檔和本機正規化規則之間有一對多的關聯性。</span><span class="sxs-lookup"><span data-stu-id="66579-404">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="66579-405">本機正規化 DNs 清單的順序必須依管理員所指定的順序來維護。</span><span class="sxs-lookup"><span data-stu-id="66579-405">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="66579-406">順序保留是由 DN 二進位的二進位部分所維護，它會指定順序索引。</span><span class="sxs-lookup"><span data-stu-id="66579-406">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="66579-407">轉寄連結： <strong>連結 ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="66579-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="66579-408">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-LocationProfileBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-409">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-410">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-411">msRTCSIP LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="66579-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="66579-412">此屬性包含正常化規則的選項清單。</span><span class="sxs-lookup"><span data-stu-id="66579-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="66579-413">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-414">msRTCSIP-LocationName (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-415">這個單一值屬性包含位置設定檔的易記名稱，表示此設定檔所代表的位置。</span><span class="sxs-lookup"><span data-stu-id="66579-415">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="66579-416">因為可以有多個位置設定檔，所以系統管理員需要一種方式來區分不同的設定檔。</span><span class="sxs-lookup"><span data-stu-id="66579-416">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="66579-417">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-418">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-419">msRTCSIP-locationProfileBL (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-420">此多重值屬性包含位置設定檔辨別名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="66579-420">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="66579-421">此屬性指定指向一或多個位置設定檔的後退連結。</span><span class="sxs-lookup"><span data-stu-id="66579-421">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="66579-422">反向連結： <strong>連結 ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="66579-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="66579-423">此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-LocalNormalizationLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-424">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-425">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-426">msRTCSIP-LocationProfileData (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-427">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-428">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-429">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-430">msRTCSIP LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="66579-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="66579-431">此屬性包含位置設定檔的選項。</span><span class="sxs-lookup"><span data-stu-id="66579-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="66579-432">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-433">msRTCSIP MappingContact</span><span class="sxs-lookup"><span data-stu-id="66579-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="66579-434">此多重值屬性包含應用程式連絡人的清單。</span><span class="sxs-lookup"><span data-stu-id="66579-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="66579-435">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-436">msRTCSIP MappingLocation</span><span class="sxs-lookup"><span data-stu-id="66579-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="66579-437">此多重值屬性包含位置設定檔的清單。</span><span class="sxs-lookup"><span data-stu-id="66579-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="66579-438">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-439">msRTCSIP-MaxNumOutstandingSearchPerServer (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-440">此屬性代表每個伺服器上的未完成搜尋要求數目上限。</span><span class="sxs-lookup"><span data-stu-id="66579-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="66579-441">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-442">msRTCSIP-MaxNumSubscriptionsPerUser (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-443">此屬性代表每位使用者的訂閱數目上限。</span><span class="sxs-lookup"><span data-stu-id="66579-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="66579-444">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-445">msRTCSIP-MaxPresenceSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-446">此屬性代表 [訂閱超時] 視窗的最大值。</span><span class="sxs-lookup"><span data-stu-id="66579-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="66579-447">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-448">msRTCSIP-MaxRegistrationsTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-449">此屬性代表 [註冊超時] 視窗的最大值。</span><span class="sxs-lookup"><span data-stu-id="66579-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="66579-450">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-452">此屬性代表最大的漫遊資料訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="66579-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="66579-453">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-454">msRTCSIP MCUData</span><span class="sxs-lookup"><span data-stu-id="66579-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="66579-455">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-456">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-457">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="66579-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="66579-458">此屬性是電腦類別下的服務控制點屬性，可指定回其所屬的 multipoint 控制項單位 (MCU) 的連結。</span><span class="sxs-lookup"><span data-stu-id="66579-458">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="66579-459">這種服務控制點和屬性是針對每家 Microsoft MCU 而建立的。</span><span class="sxs-lookup"><span data-stu-id="66579-459">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="66579-460">每個 Microsoft MCU 都必須尋找所屬集區的後端伺服器，以便從該伺服器中取得集區層級設定。</span><span class="sxs-lookup"><span data-stu-id="66579-460">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="66579-461">此屬性的值是 MCU 工廠 (DN) 的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-461">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="66579-462">這是單一值屬性，並標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="66579-462">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="66579-463">轉寄連結： <strong>連結 ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="66579-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="66579-464">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-MCUServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-465">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-466">msRTCSIP MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="66579-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="66579-467">這是多字串保留屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-467">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="66579-468">儲存在此屬性中的設定會以名稱 = 值一組來表示。</span><span class="sxs-lookup"><span data-stu-id="66579-468">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="66579-469">目前定義的 name = 值組為：</span><span class="sxs-lookup"><span data-stu-id="66579-469">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-470">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="66579-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-471">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-472">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="66579-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="66579-473">這是單一值屬性，包含與集區相關聯之單一 MCU 工廠 (DN) 的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="66579-474">轉寄連結： <strong>連結 ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="66579-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="66579-475">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-PoolAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-476">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-477">msRTCSIP MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="66579-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="66579-478">此屬性是單一值字串，用來指定 MCU 工廠提供者的 GUID。</span><span class="sxs-lookup"><span data-stu-id="66579-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="66579-479">根據 GUID 值，MCU 出廠過程會決定是否要為此 MCU 類型服務。</span><span class="sxs-lookup"><span data-stu-id="66579-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="66579-480">如果 GUID 值為 <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，則預設會在 Lync Server 中使用 MCU factory 程式 () 將會處理該流程。</span><span class="sxs-lookup"><span data-stu-id="66579-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="66579-481">對於任何其他 GUID 值，MCU 工廠處理常式將不會為 MCU 類型提供服務。</span><span class="sxs-lookup"><span data-stu-id="66579-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="66579-482">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-483">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="66579-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="66579-484">此屬性是多值的辨識名稱清單 (DN) 。</span><span class="sxs-lookup"><span data-stu-id="66579-484">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="66579-485">此屬性包含與這個 MCU 工廠相關聯之相同類型及廠商的所有 MCU 伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="66579-485">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="66579-486">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="66579-486">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="66579-487">反向連結：連結 ID 11027</span><span class="sxs-lookup"><span data-stu-id="66579-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="66579-488">此反向連結的對應正向連結是 <strong>msRTCSIP-MCUFactoryAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-489">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-490">msRTCSIP MCUType</span><span class="sxs-lookup"><span data-stu-id="66579-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="66579-491">此屬性是單一值字串，用來指定 MCU 可以處理的媒體。</span><span class="sxs-lookup"><span data-stu-id="66579-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="66579-492">支援的有效類型包括：</span><span class="sxs-lookup"><span data-stu-id="66579-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-493">會議</span><span class="sxs-lookup"><span data-stu-id="66579-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="66579-494">音訊-影片</span><span class="sxs-lookup"><span data-stu-id="66579-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="66579-495">聊天</span><span class="sxs-lookup"><span data-stu-id="66579-495">chat</span></span></p></li>
<li><p><span data-ttu-id="66579-496">電話會議</span><span class="sxs-lookup"><span data-stu-id="66579-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-497">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-498">msRTCSIP MCUVendor</span><span class="sxs-lookup"><span data-stu-id="66579-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="66579-499">此屬性是單一值字串，用來指定 MCU 廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-499">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="66579-500">所有 Microsoft MCUs 都會將此屬性指定為 <strong>Microsoft Corporation</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-500">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-501">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-502">msRTCSIP-MeetingFlags (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-503">此屬性會定義針對所有使用者或連絡人物件全域啟用的不同會議選項。</span><span class="sxs-lookup"><span data-stu-id="66579-503">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="66579-504">此屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="66579-504">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="66579-505">有效值 (和相關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="66579-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-506">0： AllowOrganizeMeetingWithAnonymousParticipants 為 None (不允許使用者邀請匿名使用者加入會議)  (未設定 bits) </span><span class="sxs-lookup"><span data-stu-id="66579-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="66579-507">4： AllowOrganizeMeetingWithAnonymousParticipants 每個人 (允許所有使用者邀請匿名使用者加入會議)  (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="66579-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="66579-508">8： AllowOrganizeMeetingWithAnonymousParticipants UsePerUserSetting (允許使用者以每位使用者的使用者邀請匿名使用者為會議設定)  (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="66579-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="66579-509">16： UserPerUserMeetingPolicy (的會議原則是針對每位使用者定義)  (位位置 4) </span><span class="sxs-lookup"><span data-stu-id="66579-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-510">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-511">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-512">msRTCSIP-MeetingPolicy (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-513">此屬性指定系統管理員為此使用者指派成單一值屬性的原則 (DN) 辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="66579-514">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-515">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-516">msRTCSIP-MinPresenceSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-517">此屬性代表最小顯示狀態訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="66579-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="66579-518">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-519">msRTCSIP-MinRegistrationTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-520">此屬性代表 [註冊超時] 視窗的最小值。</span><span class="sxs-lookup"><span data-stu-id="66579-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="66579-521">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-522">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-524">此屬性代表最小的漫遊資料訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="66579-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="66579-525">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-526">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-527">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="66579-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="66579-528">此屬性用來儲存前端集區所使用的鏡像 SQL Server 後端。</span><span class="sxs-lookup"><span data-stu-id="66579-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="66579-529">Lync Server 2013 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-530">msRTCSIP MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="66579-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="66579-531">此屬性包含定義行動性設定的選項和旗標。</span><span class="sxs-lookup"><span data-stu-id="66579-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="66579-532">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-533">msRTCSIP MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="66579-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="66579-534">此屬性包含行動性原則物件的 DN。</span><span class="sxs-lookup"><span data-stu-id="66579-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="66579-535">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-536">msRTCSIP-NumDevicesPerUser (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-537">此屬性代表允許的裝置數目，使用者可以在這些裝置上登錄 SIP 通訊並訂閱顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="66579-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="66579-538">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-539">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-540">msRTCSIP OptionFlags</span><span class="sxs-lookup"><span data-stu-id="66579-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="66579-541">此屬性會指定為 user 或 contact 物件啟用的選項。</span><span class="sxs-lookup"><span data-stu-id="66579-541">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="66579-542">此屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="66579-542">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="66579-543">每個選項都是以位表示。</span><span class="sxs-lookup"><span data-stu-id="66579-543">Each option is represented by a bit.</span></span> <span data-ttu-id="66579-544">此屬性標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="66579-544">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="66579-545">有效值 (和相關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="66579-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-546">1：啟用公用立即訊息 (IM) connectivity (位位置 0) </span><span class="sxs-lookup"><span data-stu-id="66579-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="66579-547">2：保留 (位位置 1) </span><span class="sxs-lookup"><span data-stu-id="66579-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="66579-548">4：保留 (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="66579-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="66579-549">8：保留 (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="66579-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="66579-550">16：已啟用遠端呼叫控制 [電話語音] (位位置 4) </span><span class="sxs-lookup"><span data-stu-id="66579-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="66579-551">64： AllowOrganizeMeetingWithAnonymousParticipants (允許使用者邀請匿名使用者加入會議 (位位置 6) </span><span class="sxs-lookup"><span data-stu-id="66579-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="66579-552">128： UCEnabled (啟用使用者的 UC)  (位位置 7) </span><span class="sxs-lookup"><span data-stu-id="66579-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="66579-553">256： EnabledForEnhancedPresence (啟用使用者的公用 IM 連線)  (位位置 8) </span><span class="sxs-lookup"><span data-stu-id="66579-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="66579-554">512： RemoteCallControlDualMode (位位置 9) </span><span class="sxs-lookup"><span data-stu-id="66579-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-555">使用 SP1 即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-556">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="66579-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="66579-557">在資源與中央樹系拓撲中，會使用此屬性來啟用單一登入時，當使用者從 Windows NT 伺服器主體帳戶 ObjectSID 至此屬性時，會將此屬性複製到資源或中央樹系中對應的使用者或連絡人物件的此屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="66579-558">Communicator Web Access 使用此屬性或使用者的 ObjectSID 在 AD DS 中搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="66579-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="66579-559">此屬性標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="66579-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-560">msRTCSIP OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="66579-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="66579-561">此屬性是應用程式連絡人擁有者的統一資源名稱 (URN) 。</span><span class="sxs-lookup"><span data-stu-id="66579-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="66579-562">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-563">msRTCSIP-Pattern (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-564">這個單一值字串屬性包含的模式，用來比對 e.164 格式的撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="66579-564">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="66579-565">如果撥號號碼符合此模式，就會將轉譯套用至撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="66579-565">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="66579-566">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-567">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-568">msRTCSIP-PhoneRouteBL (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-569">此多重值屬性包含電話路由辨別名稱 (DN) 清單。</span><span class="sxs-lookup"><span data-stu-id="66579-569">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="66579-570">此屬性指定指向一或多個電話路由的反向連結。</span><span class="sxs-lookup"><span data-stu-id="66579-570">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="66579-571">反向連結： <strong>連結 ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="66579-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="66579-572">此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-RouteUsageLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-573">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-574">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-575">msRTCSIP-PhoneRouteData (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-576">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-577">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-578">msRTCSIP-PhoneRouteName (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-579">這個單一值的 UNICODE 字串屬性可指定電話路由的易記名稱，以便系統管理員輕易參考該名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="66579-580">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-581">msRTCSIP-PhoneUsageData (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-582">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-583">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-584">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-585">msRTCSIP-PolicyContent (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-586">此屬性是單一值的 Unicode 字串。</span><span class="sxs-lookup"><span data-stu-id="66579-586">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="66579-587">這個字串屬性包含 XML 格式的原則定義。</span><span class="sxs-lookup"><span data-stu-id="66579-587">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="66579-588">XML 架構定義在不同的原則類型中是通用的，每個原則類型的設定值都各不相同。</span><span class="sxs-lookup"><span data-stu-id="66579-588">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="66579-589">XML 架構定義 (XSD) 定義如下：</span><span class="sxs-lookup"><span data-stu-id="66579-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="66579-590">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-591">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-592">msRTCSIP-PolicyData (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-593">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-594">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-595">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-596">msRTCSIP-PolicyType (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-597">這個單一值的 Unicode 字串屬性包含原則類型。</span><span class="sxs-lookup"><span data-stu-id="66579-597">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="66579-598">有效的原則類型如下：</span><span class="sxs-lookup"><span data-stu-id="66579-598">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-599">會議</span><span class="sxs-lookup"><span data-stu-id="66579-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="66579-600">電話</span><span class="sxs-lookup"><span data-stu-id="66579-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-601">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-602">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-603">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="66579-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="66579-604">此屬性指定的連結會傳回電腦所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="66579-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="66579-605">不論電腦正在執行 Standard Edition 還是 Lync Server Enterprise Edition，都設定此屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="66579-606">此屬性標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="66579-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="66579-607">有效的值是集區的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="66579-608">轉寄連結： <strong>連結 ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="66579-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="66579-609">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-FrontEndServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-610">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-611">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="66579-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="66579-612">此多重值屬性包含與 MCU 工廠關聯之集區 (DN) 的辨識名稱清單。</span><span class="sxs-lookup"><span data-stu-id="66579-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="66579-613">反向連結： <strong>連結 ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="66579-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="66579-614">此反向連結的對應正向連結是 <strong>msRTCSIP-MCUFactoryPath</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-615">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-616">msRTCSIP PoolData</span><span class="sxs-lookup"><span data-stu-id="66579-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="66579-617">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-618">使用 SP1 即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-619">msRTCSIP PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="66579-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="66579-620">此屬性會指定管理主控台所顯示集區的任意名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-620">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="66579-621">系統管理員可以變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-621">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="66579-622">有效的值是代表集區名稱的字串。</span><span class="sxs-lookup"><span data-stu-id="66579-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="66579-623">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-624">msRTCSIP PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="66579-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="66579-625">此屬性是單一值字串值。</span><span class="sxs-lookup"><span data-stu-id="66579-625">This attribute is a single-valued string value.</span></span> <span data-ttu-id="66579-626">當此屬性的值為時，如果系統管理員想要建立前端集區的 FQDN 不符合建立前端集區的 Active Directory 網域結構，則此屬性的值會代表集區的網域 FQDN (例如，SIP 命名空間會從網域名稱系統中脫離 (DNS) 命名空間) 。</span><span class="sxs-lookup"><span data-stu-id="66579-626">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="66579-627">建議您將前端集區域 FQDN 對應到功能變數名稱部分，以作為集區所在的 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="66579-627">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="66579-628">因此，當此屬性沒有任何值時，前端集區 FQDN 會預設為 Active Directory 功能變數名稱結構（由 <strong>dnsHostName</strong> 屬性工作表示）。</span><span class="sxs-lookup"><span data-stu-id="66579-628">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="66579-629">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-630">msRTCSIP PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="66579-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="66579-631">所有與集區相關聯之 Lync Server、Enterprise Edition Server 的功能變數名稱的多重值清單。</span><span class="sxs-lookup"><span data-stu-id="66579-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="66579-632">Type integer 的此屬性可定義集區是否可以立即訊息 (IM) 和目前狀態，以及會議。</span><span class="sxs-lookup"><span data-stu-id="66579-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="66579-633">可能的有效值類型如下：</span><span class="sxs-lookup"><span data-stu-id="66579-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-634">未定義： IM 和目前狀態服務 (即時通訊伺服器2005和 2003) </span><span class="sxs-lookup"><span data-stu-id="66579-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="66579-635">1： IM 和目前狀態服務 (Lync Server) </span><span class="sxs-lookup"><span data-stu-id="66579-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="66579-636">2： IM 及目前狀態和會議服務 (Lync Server) </span><span class="sxs-lookup"><span data-stu-id="66579-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-637">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-638">msRTCSIP PoolType</span><span class="sxs-lookup"><span data-stu-id="66579-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="66579-639">此屬性會指定伺服器集區是否正在執行 Standard Edition server 或 Enterprise Edition server。</span><span class="sxs-lookup"><span data-stu-id="66579-639">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="66579-640">此屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="66579-640">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="66579-641">每個選項都是以位表示。</span><span class="sxs-lookup"><span data-stu-id="66579-641">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="66579-642">有效值 (和相關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="66579-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-643">1： Standard Edition server，主控使用者 (位位置 0) </span><span class="sxs-lookup"><span data-stu-id="66579-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="66579-644">2： Enterprise Edition 伺服器，主控使用者 (位位置 1) </span><span class="sxs-lookup"><span data-stu-id="66579-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="66579-645">4： Standard Edition server，主控應用程式 (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="66579-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="66579-646">8： Enterprise Edition 伺服器，主控應用程式 (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="66579-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="66579-647">因為 Lync Server 不支援僅裝載應用程式的集區，所以唯一有效的值如下：</span><span class="sxs-lookup"><span data-stu-id="66579-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-648">5： Standard Edition server，主控使用者和應用程式 (位位置0和 2) </span><span class="sxs-lookup"><span data-stu-id="66579-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="66579-649">10： Enterprise Edition 伺服器，主控使用者和應用程式 (位位置1和 3) </span><span class="sxs-lookup"><span data-stu-id="66579-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-650">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-651">msRTCSIP PoolVersion</span><span class="sxs-lookup"><span data-stu-id="66579-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="66579-652">此屬性會定義集區的版本。</span><span class="sxs-lookup"><span data-stu-id="66579-652">This attribute defines the pool version.</span></span> <span data-ttu-id="66579-653">它是一種每一主要產品版本遞增的整數類型。</span><span class="sxs-lookup"><span data-stu-id="66579-653">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="66579-654">可能的有效值類型如下：</span><span class="sxs-lookup"><span data-stu-id="66579-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-655">0： Live 通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="66579-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="66579-656">1： Live 通訊伺服器2005</span><span class="sxs-lookup"><span data-stu-id="66579-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="66579-657">2： Live 通訊伺服器2005與 SP1</span><span class="sxs-lookup"><span data-stu-id="66579-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="66579-658">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="66579-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="66579-659">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="66579-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="66579-660">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="66579-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-661">即時通訊伺服器2005與 SP1。</span><span class="sxs-lookup"><span data-stu-id="66579-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-662">msRTCSIP PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="66579-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="66579-663">此屬性包含定義顯示狀態設定的選項和旗標。</span><span class="sxs-lookup"><span data-stu-id="66579-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="66579-664">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-665">msRTCSIP Microsoft.rtc.management.writableconfig.policy.presence.presencepolicy</span><span class="sxs-lookup"><span data-stu-id="66579-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="66579-666">此屬性包含目前狀態原則物件的 DN。</span><span class="sxs-lookup"><span data-stu-id="66579-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="66579-667">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-668">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="66579-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="66579-669">此屬性可讓使用者或連絡人進行 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="66579-669">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="66579-670">因為在中央樹系拓撲中，連絡人物件（而非使用者物件）已啟用 SIP，所以它會新增至連絡人類別。</span><span class="sxs-lookup"><span data-stu-id="66579-670">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="66579-671">有效值是使用者所在之 Standard Edition server 或 Enterprise Edition 前端集區的 DN。</span><span class="sxs-lookup"><span data-stu-id="66579-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="66579-672">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-673">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="66579-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="66579-674">此屬性包含指定使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="66579-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-675">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="66579-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="66579-676">此屬性包含專用線路裝置的設備識別碼。</span><span class="sxs-lookup"><span data-stu-id="66579-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="66579-677">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-678">msRTCSIP 路由</span><span class="sxs-lookup"><span data-stu-id="66579-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="66579-679">此屬性是 Boolean 屬性，用來判斷是否已授權 Lync Server 使用其 GRUU 位址路由傳送至此服務。</span><span class="sxs-lookup"><span data-stu-id="66579-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="66579-680">如果此值設為 <strong>TRUE</strong>，則會授權 Lync Server 路由傳送至此服務。</span><span class="sxs-lookup"><span data-stu-id="66579-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="66579-681">如果此值設為 <strong>FALSE</strong>，Lync Server 就不會獲得路由傳送到此服務的授權。</span><span class="sxs-lookup"><span data-stu-id="66579-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="66579-682">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-683">msRTCSIP-RouteUsageAttribute (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-684">這個單一值的 UNICODE 字串屬性定義的屬性會限定電話路由的使用方式。</span><span class="sxs-lookup"><span data-stu-id="66579-684">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="66579-685">電話路由的選取取決於兩個元素：指派給電話路由的使用方式屬性，以及來電者的允許原則使用屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-685">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="66579-686">已選取具有與來電者允許之使用狀況屬性相符的第一個電話路由。</span><span class="sxs-lookup"><span data-stu-id="66579-686">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="66579-687">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-688">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-689">msRTCSIP-RouteUsageLinks (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-690">此多重值辨別名稱 (DN) 屬性包含路由流量辨別名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="66579-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="66579-691">轉寄連結： <strong>連結 ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="66579-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="66579-692">此屬性是對應的反向連結 <strong>msRTCSIP-PhoneRouteBL</strong>的向前連結。</span><span class="sxs-lookup"><span data-stu-id="66579-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-693">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-694">msRTCSIP RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="66579-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="66579-695">此屬性包含 DN，該 DN 指向所有 SIP 流量定址至此 MCU 或受信任的服務必須經過的集區。</span><span class="sxs-lookup"><span data-stu-id="66579-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="66579-696">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-697">msRTCSIP-RuleName (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-698">這個單一值的 UNICODE 字串屬性會指定正規化規則的易記名稱，因此系統管理員可以輕易參考該名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="66579-699">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-700">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-701">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="66579-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="66579-702">此屬性代表組織中目前部署的架構版本。</span><span class="sxs-lookup"><span data-stu-id="66579-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-703">msRTCSIP-SearchMaxRequests (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-704">當使用者使用 Communicator 搜尋連絡人時，此屬性會限制目錄搜尋傳回的搜尋結果數目。</span><span class="sxs-lookup"><span data-stu-id="66579-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="66579-705">此屬性會覆寫用戶端提供的值。</span><span class="sxs-lookup"><span data-stu-id="66579-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="66579-706">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-707">msRTCSIP-SearchMaxResults (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-708">此屬性會限制傳回的搜尋要求數目。</span><span class="sxs-lookup"><span data-stu-id="66579-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="66579-709">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-710">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="66579-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="66579-711">此多重值屬性是一個 back 連結，其中包含可辨識名稱清單 (DN) 。</span><span class="sxs-lookup"><span data-stu-id="66579-711">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="66579-712">這些 DNs 指向集區或 <strong>TrustedService</strong> 物件。</span><span class="sxs-lookup"><span data-stu-id="66579-712">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="66579-713">此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-TrustedServiceLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-714">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-715">msRTCSIP ServerData</span><span class="sxs-lookup"><span data-stu-id="66579-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="66579-716">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-717">msRTCSIP-ServerReferenceBL (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-718">此多重值屬性包含辨識名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="66579-718">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="66579-719">這些辨別名稱是指參照其他可指派預設位置設定檔之伺服器物件的連結。</span><span class="sxs-lookup"><span data-stu-id="66579-719">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="66579-720">反向連結： <strong>連結 ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="66579-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="66579-721">此反向連結的對應正向連結是 <strong>msRTCSIP-DefaultLocationProfileLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="66579-722">此反向連結屬性只會參照集區和轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="66579-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="66579-723">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-724">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-725">msRTCSIP ServerVersion</span><span class="sxs-lookup"><span data-stu-id="66579-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="66579-726">此屬性會定義伺服器的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="66579-726">This attribute defines the version information of the server.</span></span> <span data-ttu-id="66579-727">此版本編號適用于所有伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="66579-727">This version number applies to all server roles.</span></span> <span data-ttu-id="66579-728">它是隨每個官方產品發行增加的 monotonously 增加整數。</span><span class="sxs-lookup"><span data-stu-id="66579-728">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="66579-729">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="66579-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-730">未定義： Live 通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="66579-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="66579-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="66579-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="66579-732">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="66579-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="66579-733">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="66579-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="66579-734">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="66579-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="66579-735">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="66579-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="66579-736">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66579-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-737">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-738">msRTCSIP SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="66579-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="66579-739">整數類型的這個單一值屬性指定 <strong>msDS-SourceObjectDN</strong> 指向的物件類型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="66579-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-740">null |0x00000001：代表來自不同樹系的 Windows NT 伺服器主體使用者物件</span><span class="sxs-lookup"><span data-stu-id="66579-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="66579-741">下列屬性代表通訊群組擴充的不同樹系中的群組類型：</span><span class="sxs-lookup"><span data-stu-id="66579-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-742">0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="66579-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="66579-743">0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="66579-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="66579-744">0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="66579-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="66579-745">0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="66579-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="66579-746">0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="66579-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="66579-747">0x90000000：代表來自相同樹系或不同樹系的自動語音應答或訂戶存取物件</span><span class="sxs-lookup"><span data-stu-id="66579-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="66579-748">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-749">msRTCSIP-SubscriptionAuthRequired (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-750">在即時通訊伺服器2003中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="66579-751">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-752">msRTCSIP TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="66579-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="66579-753">此屬性可讓您將使用者或連絡人物件從一個 Lync 伺服器集區移至另一個。</span><span class="sxs-lookup"><span data-stu-id="66579-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="66579-754">此屬性會新增至連絡人類別，因為在中央樹系拓撲中，連絡人物件（而非使用者物件）已啟用 SIP。</span><span class="sxs-lookup"><span data-stu-id="66579-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="66579-755">有效值是要移動使用者之目的地 Standard Edition 伺服器或前端集區的 DN。</span><span class="sxs-lookup"><span data-stu-id="66579-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="66579-756">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-757">msRTCSIP-TargetPhoneNumber (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-758">這個單一值字串屬性包含電話號碼模式或範圍，以路由傳送至 <strong>msRTCSIP-Gateways</strong>中定義的指定閘道。</span><span class="sxs-lookup"><span data-stu-id="66579-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-759">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-760">msRTCSIP TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="66579-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="66579-761">此屬性會儲存 Lync Server 使用者之目標原則的名稱-值對。</span><span class="sxs-lookup"><span data-stu-id="66579-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="66579-762">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-763">msRTCSIP TenantId</span><span class="sxs-lookup"><span data-stu-id="66579-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="66579-764">此屬性會儲存租使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="66579-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="66579-765">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-766">msRTCSIP-Translation (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-767">此屬性是 Lync Server 的語音功能使用的，且包含翻譯字串以套用至撥號號碼（如果找到相符的號碼）。</span><span class="sxs-lookup"><span data-stu-id="66579-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="66579-768">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="66579-769">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-770">msRTCSIP TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="66579-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="66579-771">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-772">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-773">msRTCSIP TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="66579-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="66579-774">此屬性是包含 MCU FQDN 的字串值。</span><span class="sxs-lookup"><span data-stu-id="66579-774">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="66579-775">這是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-775">This is a single-valued attribute.</span></span> <span data-ttu-id="66579-776">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="66579-776">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="66579-777">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-778">msRTCSIP TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="66579-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="66579-779">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-780">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-781">msRTCSIP TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="66579-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="66579-782">此屬性是包含執行 Proxy 伺服器之伺服器的 FQDN 的字串值。</span><span class="sxs-lookup"><span data-stu-id="66579-782">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="66579-783">此屬性是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-783">This attribute is single-valued.</span></span> <span data-ttu-id="66579-784">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="66579-784">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="66579-785">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-786">msRTCSIP TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="66579-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="66579-787">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-788">msRTCSIP TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="66579-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="66579-789">此屬性是單一值屬性，代表受信任伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="66579-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="66579-790">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-791">msRTCSIP TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="66579-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="66579-792">此屬性會指定受信任的伺服器清單中伺服器的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="66579-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="66579-793">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="66579-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-794">Null： Live 通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="66579-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="66579-795">2： Live 通訊伺服器2005</span><span class="sxs-lookup"><span data-stu-id="66579-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="66579-796">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="66579-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="66579-797">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="66579-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="66579-798">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="66579-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="66579-799">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66579-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-800">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-801">msRTCSIP TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="66579-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="66579-802">此屬性會定義為受信任的服務啟用的選項。</span><span class="sxs-lookup"><span data-stu-id="66579-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="66579-803">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-804">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="66579-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="66579-805">此多重值屬性包含辨識名稱清單 (DN) 參考信任的服務物件，例如媒體轉送驗證服務。</span><span class="sxs-lookup"><span data-stu-id="66579-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="66579-806">執行 A/V 會議服務之 Edge Server 上的媒體轉送驗證服務 (實際組合) 必須與集區相關聯，以支援遠端使用者的音訊案例。</span><span class="sxs-lookup"><span data-stu-id="66579-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="66579-807">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-ServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-808">Uc</span><span class="sxs-lookup"><span data-stu-id="66579-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-809">msRTCSIP TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="66579-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="66579-810">此屬性是一個整數，用來定義用來連線到此 GRUU 服務的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="66579-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="66579-811">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-812">msRTCSIP TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="66579-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="66579-813">此屬性是定義其所代表之 GRUU 服務類型的字串值。</span><span class="sxs-lookup"><span data-stu-id="66579-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="66579-814">有效的 GRUU 服務類型如下：</span><span class="sxs-lookup"><span data-stu-id="66579-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="66579-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="66579-816">閘道</span><span class="sxs-lookup"><span data-stu-id="66579-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="66579-817">媒體轉送驗證服務 (MRAS) </span><span class="sxs-lookup"><span data-stu-id="66579-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="66579-818">QoSM</span><span class="sxs-lookup"><span data-stu-id="66579-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="66579-819">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="66579-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-820">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-821">msRTCSIP TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="66579-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="66579-822">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-823">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-824">msRTCSIP TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="66579-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="66579-825">此屬性是包含執行 Lync Server Web 服務之 IIS 之 FQDN 的字串值。</span><span class="sxs-lookup"><span data-stu-id="66579-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="66579-826">這是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-826">This is a single-valued attribute.</span></span> <span data-ttu-id="66579-827">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="66579-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="66579-828">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-829">msRTCSIP-UCFlags (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-830">此屬性定義不同的 UC 選項，可供全域對所有的使用者或連絡人物件啟用。</span><span class="sxs-lookup"><span data-stu-id="66579-830">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="66579-831">此屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="66579-831">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="66579-832">每個選項都是以一位的狀態來表示。</span><span class="sxs-lookup"><span data-stu-id="66579-832">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="66579-833">可能有效的值 (和關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="66579-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-834">4： UsePerUserUCPolicy (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="66579-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="66579-835">設定此位時，即會定義每位使用者的 UC 原則。</span><span class="sxs-lookup"><span data-stu-id="66579-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="66579-836">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-837">msRTCSIP-UCPolicy (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-838">這個單一值屬性包含系統管理員為此使用者指派的 UC 原則 (DN) 辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="66579-839">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-840">msRTCSIP-UserDomainList (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66579-841">此屬性提供樹系中所有主控 SIP-enabled 使用者的網域清單。</span><span class="sxs-lookup"><span data-stu-id="66579-841">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="66579-842">預設值為空白清單，表示樹系中的所有網域都已 SIP-enabled。</span><span class="sxs-lookup"><span data-stu-id="66579-842">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="66579-843">有效的值為多個字串，代表個別網域的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="66579-844">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="66579-845">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-846">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="66579-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="66579-847">此屬性會決定使用者目前是否已啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="66579-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-848">msRTCSIP UserExtension</span><span class="sxs-lookup"><span data-stu-id="66579-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="66579-849">此多重值屬性以 name = value 的格式包含名稱-值對的清單 &quot; 。 &quot; 此屬性標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="66579-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="66579-850">使用 SP1 即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-851">msRTCSIP UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="66579-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="66579-852">此屬性包含指向位置設定檔物件 (DN) 的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="66579-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="66579-853">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-854">msRTCSIP UserPolicies</span><span class="sxs-lookup"><span data-stu-id="66579-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="66579-855">此屬性儲存使用者原則的名稱-值對。</span><span class="sxs-lookup"><span data-stu-id="66579-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="66579-856">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-857">msRTCSIP UserPolicy</span><span class="sxs-lookup"><span data-stu-id="66579-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="66579-858">這是多重值屬性，包含具有二進位 (DN_WITH_BINARY) 指向全域使用者原則的不同類型的辨識名稱清單。</span><span class="sxs-lookup"><span data-stu-id="66579-858">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="66579-859">二進位部分會指出 DN 部分指向的原則類型。</span><span class="sxs-lookup"><span data-stu-id="66579-859">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="66579-860">有效的二進位值如下：</span><span class="sxs-lookup"><span data-stu-id="66579-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-861">0x00000001：會議原則</span><span class="sxs-lookup"><span data-stu-id="66579-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="66579-862">0x00000002： UC 原則</span><span class="sxs-lookup"><span data-stu-id="66579-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="66579-863">0x00000005：顯示狀態原則</span><span class="sxs-lookup"><span data-stu-id="66579-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-864">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-865">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="66579-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="66579-866">這是 SIP 路由群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="66579-866">This is the SIP routing group ID.</span></span> <span data-ttu-id="66579-867">相同群組中的使用者會註冊到同一個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="66579-867">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="66579-868">Lync Server 2013 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-869">msRTCSIP WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="66579-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="66579-870">這是多重值屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-870">This is a multi-valued attribute.</span></span> <span data-ttu-id="66579-871">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="66579-871">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="66579-872">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-873">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="66579-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="66579-874">這個單一值屬性會指向網頁元件所屬的集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="66579-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="66579-875">轉寄連結： <strong>連結 ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="66579-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="66579-876">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-WebComponentsServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-877">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-878">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="66579-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="66579-879">此屬性是多重值的辨識名稱清單。</span><span class="sxs-lookup"><span data-stu-id="66579-879">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="66579-880">此屬性包含與此集區相關聯之所有網頁伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="66579-880">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="66579-881">反向連結： <strong>連結 ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="66579-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="66579-882">此反向連結的對應正向連結是 <strong>msRTCSIP-WebComponentsPoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="66579-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="66579-883">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="66579-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-884">msRTCSIP-WMIInstanceId (過時) </span><span class="sxs-lookup"><span data-stu-id="66579-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="66579-885">在即時通訊伺服器2003中新增。</span><span class="sxs-lookup"><span data-stu-id="66579-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="66579-886">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="66579-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="66579-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="66579-888">電話語音會使用這個現有的 Active Directory 屬性來指定電話的備用 TCP/IP 地址清單。</span><span class="sxs-lookup"><span data-stu-id="66579-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="66579-889">Windows Server 2008 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-890">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="66579-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="66579-891">Lync Server 中的語音元件會使用這個現有的 Active Directory 屬性，針對連絡人物件，以供路由呼叫至整合通訊自動語音應答和使用者存取號碼的目的。</span><span class="sxs-lookup"><span data-stu-id="66579-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="66579-892">無條件呼叫轉寄位址會儲存在此多重值屬性中。</span><span class="sxs-lookup"><span data-stu-id="66579-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="66579-893">此帳戶是針對自動語音應答和使用者存取的特定用途而建立。</span><span class="sxs-lookup"><span data-stu-id="66579-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="66579-894">管理員不應修改這個帳戶的屬性。</span><span class="sxs-lookup"><span data-stu-id="66579-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="66579-895">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66579-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="66579-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="66579-897">這個現有的 Active Directory 多重值屬性是 Windows 2000 中所引進之基礎 Active Directory 架構的一部分。</span><span class="sxs-lookup"><span data-stu-id="66579-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="66579-898">此屬性包含使用者電子郵件的各種 X400、X500 及 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="66579-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="66579-899">在即時通訊伺服器2003和更新版本中，會使用 [sip：] 標記將使用者的 SIP URI 新增至此清單 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="66579-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="66579-900">下列應用程式會從此屬性搜尋使用者的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="66579-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="66579-901">Microsoft Office Outlook 2003 訊息與共同作業用戶端</span><span class="sxs-lookup"><span data-stu-id="66579-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="66579-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="66579-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66579-903">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66579-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="66579-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="66579-905">這個現有的 Active Directory 屬性包含使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="66579-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="66579-906">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66579-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

