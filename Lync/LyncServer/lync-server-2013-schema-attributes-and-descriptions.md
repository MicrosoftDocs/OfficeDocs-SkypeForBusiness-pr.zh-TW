---
title: Lync Server 2013：架構屬性和描述
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
ms.openlocfilehash: bcd4c3f3da44be2721d1c6bfc1c1ceece47b6232
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510870"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="3822f-102">Lync Server 2013 中的架構屬性和描述</span><span class="sxs-lookup"><span data-stu-id="3822f-102">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3822f-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3822f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3822f-104">本節說明 Lync Server 2013 所使用的所有架構屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="3822f-105">如需與屬性相關聯的類別，請參閱 [在 Lync Server 2013 中依類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="3822f-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="3822f-106">如需 Lync Server 2013 中新的類別和屬性清單，請參閱 [Lync server 2013 中的架構變更](lync-server-2013-schema-changes-in-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="3822f-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="3822f-107">連結成對的屬性會指定為正向連結或反向連結。</span><span class="sxs-lookup"><span data-stu-id="3822f-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="3822f-108">參照至另一個物件的屬性是轉寄連結;參照至第一個物件的另一個物件的屬性是 back 連結。</span><span class="sxs-lookup"><span data-stu-id="3822f-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="3822f-109">轉寄連結是可更新的，而 back 連結是唯讀的。</span><span class="sxs-lookup"><span data-stu-id="3822f-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="3822f-110">有些屬性具有位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="3822f-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="3822f-111">針對這些屬性，每個設定都是以位表示，顯示的十進位值代表位位置。</span><span class="sxs-lookup"><span data-stu-id="3822f-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="3822f-112">位位置以位0開始。</span><span class="sxs-lookup"><span data-stu-id="3822f-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="3822f-113">例如，1 (二進位) 為 bit 0 設定，而 10000 (二進位) 是位4集。</span><span class="sxs-lookup"><span data-stu-id="3822f-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="3822f-114">每個位代表一個屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-114">Each bit represents a property.</span></span> <span data-ttu-id="3822f-115">以下是一些範例：</span><span class="sxs-lookup"><span data-stu-id="3822f-115">The following are some examples:</span></span>

  - <span data-ttu-id="3822f-116">10000 (二進位) 具有十進位值 16 (，也就是設定) 的位4。</span><span class="sxs-lookup"><span data-stu-id="3822f-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="3822f-117">100000000 (二進位) 的十進位值為 256 (也就是設定) 的位8。</span><span class="sxs-lookup"><span data-stu-id="3822f-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="3822f-118">1100 (二進位) 的十進位值為 12 (，也就是設定位2和 3;) 啟用兩個位代表的屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="3822f-119">1111000001 (二進位) 具有十進位值 961 (也就是設定位0、6、7、8和9。這兩個位的屬性都已) 啟用。</span><span class="sxs-lookup"><span data-stu-id="3822f-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="3822f-120">Lync Server 2013 的架構屬性</span><span class="sxs-lookup"><span data-stu-id="3822f-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3822f-121">屬性</span><span class="sxs-lookup"><span data-stu-id="3822f-121">Attribute</span></span></th>
<th><span data-ttu-id="3822f-122">描述</span><span class="sxs-lookup"><span data-stu-id="3822f-122">Description</span></span></th>
<th><span data-ttu-id="3822f-123">註解</span><span class="sxs-lookup"><span data-stu-id="3822f-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3822f-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="3822f-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="3822f-125">現在與 <strong>MsRTCSIP 集</strong> 區及 <strong>msRTCSIP MonitoringServer</strong> 類別相關聯之 Active Directory 網域服務中的現有屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="3822f-126">此屬性會指定集區或監控伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="3822f-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="3822f-127">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="3822f-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3822f-128">Microsoft Office Live 通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="3822f-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="3822f-130">此屬性包含另一個樹系中物件的辨識名稱 (DN) 的字串標記法，該物件會對應至此物件。</span><span class="sxs-lookup"><span data-stu-id="3822f-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="3822f-131">此屬性用於通訊群組擴充和自動出勤。</span><span class="sxs-lookup"><span data-stu-id="3822f-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="3822f-132">此屬性是在 Windows Server 2003 R2 的預設 Active Directory 架構中定義的。</span><span class="sxs-lookup"><span data-stu-id="3822f-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="3822f-133">為了避免需要將 AD DS 升級為 Windows Server 2003 R2，Active Directory 架構準備會以此屬性定義延伸 Windows Server 2003 架構。</span><span class="sxs-lookup"><span data-stu-id="3822f-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="3822f-134">Microsoft Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3822f-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="3822f-136">此多重值屬性包含語音信箱設定。</span><span class="sxs-lookup"><span data-stu-id="3822f-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="3822f-137">此屬性與 Exchange 整合通訊 (UM) 共用。</span><span class="sxs-lookup"><span data-stu-id="3822f-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="3822f-138">Microsoft Lync Server 2010 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="3822f-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="3822f-140">此多重值屬性包含適用于使用者之保留原則的識別碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="3822f-141">保留原則會在保留期間保留使用者的信箱專案。</span><span class="sxs-lookup"><span data-stu-id="3822f-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="3822f-142">此屬性與 Exchange 2013 共用。</span><span class="sxs-lookup"><span data-stu-id="3822f-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="3822f-143">Lync Server 2013 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-144">msRTCSIP AcpInfo</span><span class="sxs-lookup"><span data-stu-id="3822f-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="3822f-145">此屬性會儲存使用者的音訊會議提供者資訊。</span><span class="sxs-lookup"><span data-stu-id="3822f-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="3822f-146">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-147">msRTCSIP ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="3822f-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="3822f-148">此屬性指向應用程式連絡人的信任服務專案。</span><span class="sxs-lookup"><span data-stu-id="3822f-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="3822f-149">Microsoft Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-150">msRTCSIP ApplicationList</span><span class="sxs-lookup"><span data-stu-id="3822f-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="3822f-151">此屬性包含應用程式伺服器上的主控應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="3822f-152">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-153">msRTCSIP ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="3822f-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="3822f-154">此屬性會指定應用程式連絡人的選項。</span><span class="sxs-lookup"><span data-stu-id="3822f-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="3822f-155">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-156">msRTCSIP ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="3822f-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="3822f-157">此屬性包含應用程式連絡人的主要語言。</span><span class="sxs-lookup"><span data-stu-id="3822f-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="3822f-158">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-159">msRTCSIP ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="3822f-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="3822f-160">此多重值屬性包含應用程式連絡人的次要語言。</span><span class="sxs-lookup"><span data-stu-id="3822f-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="3822f-161">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-162">msRTCSIP ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="3822f-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="3822f-163">此屬性包含隸屬于此集區的應用程式伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="3822f-164">此反向連結屬性的對應正向連結是 <strong>msRTCSIP-ApplicationServerPoolLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-165">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-166">msRTCSIP ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="3822f-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="3822f-167">此屬性指向此應用程式伺服器所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="3822f-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="3822f-168">這是轉寄連結。</span><span class="sxs-lookup"><span data-stu-id="3822f-168">This is the forward link.</span></span> <span data-ttu-id="3822f-169">對應的 [反向] 連結是 <strong>msRTCSIP-ApplicationServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-170">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-171">msRTCSIP-ArchiveDefault (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-172">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-173">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-174">msRTCSIP-ArchiveDefaultFlags (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-175">此屬性指定樹系界限內的全域預設值，以封存所有使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3822f-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="3822f-176">這是由封存代理程式層強制執行。</span><span class="sxs-lookup"><span data-stu-id="3822f-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="3822f-177">此屬性的值範圍如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-178"><strong>TRUE</strong>：封存所有使用者</span><span class="sxs-lookup"><span data-stu-id="3822f-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="3822f-179"><strong>FALSE</strong>：不封存所有使用者</span><span class="sxs-lookup"><span data-stu-id="3822f-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="3822f-180">此屬性會在樹系界限內，全域控制如何封存內部網路中的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3822f-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="3822f-181"><strong>即時通訊伺服器2005行為 (現已撤銷) </strong></span><span class="sxs-lookup"><span data-stu-id="3822f-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="3822f-182">此屬性的值範圍如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-183">0：封存郵件本文 [位 0]</span><span class="sxs-lookup"><span data-stu-id="3822f-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="3822f-184">1：不要封存郵件本文 [位 0]</span><span class="sxs-lookup"><span data-stu-id="3822f-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="3822f-185"><strong>Office 通訊伺服器2007行為</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="3822f-186">此屬性的值範圍如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-187">0： ArchiveFederationDefaultWithoutBody (撤銷) </span><span class="sxs-lookup"><span data-stu-id="3822f-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="3822f-188">1-2： ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="3822f-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="3822f-189">3-4： ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="3822f-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="3822f-190">5： RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="3822f-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="3822f-191">6： RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="3822f-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3822f-192">7： RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="3822f-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3822f-193">8： RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="3822f-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="3822f-194">9： RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="3822f-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3822f-195">10： RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="3822f-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3822f-196">11： RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="3822f-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3822f-197">12： RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="3822f-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="3822f-198">13： RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="3822f-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="3822f-199">14： RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="3822f-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="3822f-200">15： RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="3822f-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="3822f-201">16： RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="3822f-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-202">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-203">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-204">msRTCSIP-ArchiveFederationDefault (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-205">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-206">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-207">msRTCSIP-ArchiveFederationDefaultFlags (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-208">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-209">在 Office 通訊伺服器2007中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-210">msRTCSIP ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="3822f-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="3822f-211">此屬性是一種整數，用來控制是否要封存單一使用者的通訊的位欄位。</span><span class="sxs-lookup"><span data-stu-id="3822f-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="3822f-212">此控制項是由封存代理程式層強制執行。</span><span class="sxs-lookup"><span data-stu-id="3822f-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="3822f-213">它會標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="3822f-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3822f-214">此屬性的範圍是單一使用者或連絡人特有的。</span><span class="sxs-lookup"><span data-stu-id="3822f-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="3822f-215">在 Lync Server 中)  (和關聯位位置的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-216">0：不封存 (未設定任何位) </span><span class="sxs-lookup"><span data-stu-id="3822f-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="3822f-217">1：已撤銷 (位位置 0) </span><span class="sxs-lookup"><span data-stu-id="3822f-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="3822f-218">2：已撤銷 (位位置 1) </span><span class="sxs-lookup"><span data-stu-id="3822f-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="3822f-219">4：封存內部通訊 (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="3822f-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3822f-220">8：封存同盟通訊 (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="3822f-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="3822f-221">Live 迅 Server 2005 中先前有效的值如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-222">0：使用依下列優先順序 <strong>msRTCSIP-ArchiveDefault</strong> 和 <strong>msRTCSIP-ArchiveFederation</strong> 所定義的預設值：</span><span class="sxs-lookup"><span data-stu-id="3822f-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-223">1：封存</span><span class="sxs-lookup"><span data-stu-id="3822f-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="3822f-224">2：不要封存</span><span class="sxs-lookup"><span data-stu-id="3822f-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="3822f-225">3：不含郵件內文的封存</span><span class="sxs-lookup"><span data-stu-id="3822f-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="3822f-226">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-227">msRTCSIP-ArchivingServerData (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-228">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-229">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-230">msRTCSIP-ArchivingServerVersion (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-231">此屬性會定義封存服務的版本。</span><span class="sxs-lookup"><span data-stu-id="3822f-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="3822f-232">此屬性是隨每個官方產品發行增加的 monotonously 增加整數類型。</span><span class="sxs-lookup"><span data-stu-id="3822f-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="3822f-233">可能的有效值為：</span><span class="sxs-lookup"><span data-stu-id="3822f-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-234">未定義： Live 通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="3822f-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="3822f-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="3822f-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="3822f-236">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="3822f-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="3822f-237">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="3822f-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="3822f-238">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3822f-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-239">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-240">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-241">msRTCSIP BackEndServer</span><span class="sxs-lookup"><span data-stu-id="3822f-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="3822f-242">此屬性指定集區後端伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3822f-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="3822f-243">因為每個集區只能有一個後端伺服器，所以這是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="3822f-244">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="3822f-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3822f-245">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-246">msRTCSIP ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="3822f-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="3822f-247">此屬性包含主控會議目錄之集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="3822f-248">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-249">msRTCSIP ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="3822f-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="3822f-250">此屬性包含會議目錄的識別碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="3822f-251">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-252">msRTCSIP ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="3822f-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="3822f-253">此屬性包含會議目錄移動所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="3822f-254">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-255">msRTCSIP-預設值</span><span class="sxs-lookup"><span data-stu-id="3822f-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="3822f-256">這個 Boolean 屬性定義電話使用方式是否為預設使用量。</span><span class="sxs-lookup"><span data-stu-id="3822f-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="3822f-257">如果此屬性設定為 <strong>TRUE</strong>，則系統會使用電話的預設值，且無法由系統管理員刪除。</span><span class="sxs-lookup"><span data-stu-id="3822f-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="3822f-258">如果此屬性設為 <strong>FALSE</strong>，則可刪除使用方式。</span><span class="sxs-lookup"><span data-stu-id="3822f-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="3822f-259">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-260">msRTCSIP DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="3822f-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="3822f-261">此屬性會識別組織外部使用者的 Communicator Web Access URL。</span><span class="sxs-lookup"><span data-stu-id="3822f-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="3822f-262">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-263">msRTCSIP DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="3822f-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="3822f-264">此屬性會識別組織內部使用者的 Communicator Web Access URL。</span><span class="sxs-lookup"><span data-stu-id="3822f-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="3822f-265">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-266">msRTCSIP-DefaultLocationProfileLink (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-267">這個單一值屬性包含指派給它的位置設定檔類別物件 (DN) 的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="3822f-268">轉寄連結： <strong>連結 ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="3822f-269">對應的反向連結 <strong>msRTCSIP-ServerReferenceBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-270">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-271">msRTCSIP-DefaultPolicy (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-272">這個布林值屬性指定原則是否為預設原則。</span><span class="sxs-lookup"><span data-stu-id="3822f-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="3822f-273">原則是設定為 <strong>TRUE</strong>時的預設原則。</span><span class="sxs-lookup"><span data-stu-id="3822f-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-274">Office 通訊伺服器2007的新增功能</span><span class="sxs-lookup"><span data-stu-id="3822f-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="3822f-275">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-276">msRTCSIP-DefaultRouteToEdgeProxy (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-277">此屬性指定執行 Access Edge service 之 Edge Server 的 FQDN （如果可以直接存取），或指定執行 Access Edge service 之伺服器集區的硬體負載平衡器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3822f-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="3822f-278">如果執行 Access Edge service 的伺服器只能透過一或多個 Director 存取，則此屬性會指定 FQDN，並選擇性地指定 Director 或硬體負載平衡器服務 Director 集區的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="3822f-279">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="3822f-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3822f-280">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-281">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-282">msRTCSIP-DefaultRouteToEdgeProxyPort (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-283">此屬性代表應該用來連線至執行 Access Edge service 之伺服器的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="3822f-284">有效的值是指定要使用的埠的整數值。</span><span class="sxs-lookup"><span data-stu-id="3822f-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="3822f-285">預設值為5061。</span><span class="sxs-lookup"><span data-stu-id="3822f-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="3822f-286">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-287">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-288">msRTCSIP-DefPresenceSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-289">此屬性代表預設的目前狀態訂閱超時期間。</span><span class="sxs-lookup"><span data-stu-id="3822f-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="3822f-290">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-291">msRTCSIP-DefRegistrationTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-292">此屬性代表預設的註冊超時視窗。</span><span class="sxs-lookup"><span data-stu-id="3822f-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3822f-293">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-295">此屬性代表預設的漫遊資料訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="3822f-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3822f-296">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-297">msRTCSIP DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="3822f-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="3822f-298">此屬性會用於分割的網域拓撲，並包含完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="3822f-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="3822f-299">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-300">msRTCSIP-Description (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-301">這個單一值的 UNICODE 字串屬性包含此電話路由或正常化規則的易記描述。</span><span class="sxs-lookup"><span data-stu-id="3822f-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="3822f-302">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-303">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-304">msRTCSIP DomainData</span><span class="sxs-lookup"><span data-stu-id="3822f-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="3822f-305">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="3822f-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="3822f-307">此屬性代表針對註冊機構所設定的網域。</span><span class="sxs-lookup"><span data-stu-id="3822f-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-308">msRTCSIP EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="3822f-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="3822f-309">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-310">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-311">msRTCSIP EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="3822f-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="3822f-312">此屬性指定執行 Access Edge service 之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3822f-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="3822f-313">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="3822f-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3822f-314">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-315">msRTCSIP-EnableBestEffortNotify (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-316">此屬性會控制伺服器是否會產生最佳的努力，以回應用戶端的訂閱要求 (BENOTIFY) 要求，而不是通知要求。</span><span class="sxs-lookup"><span data-stu-id="3822f-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="3822f-317">BENOTIFY 是對訂閱通知握手的效能擴充擴充，伺服器會產生 BENOTIFY 要求，而不是一般通知要求。</span><span class="sxs-lookup"><span data-stu-id="3822f-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="3822f-318">效能好處是 BENOTIFY 要求不需要用戶端的 200 OK 回應，因為 NOTIFY 要求會執行。</span><span class="sxs-lookup"><span data-stu-id="3822f-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="3822f-319">有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3822f-320">即時通訊伺服器2003不支援 BENOTIFY 要求。</span><span class="sxs-lookup"><span data-stu-id="3822f-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="3822f-321">若要與使用 live 迅 Server 2005 和協力廠商伺服器上執行的即時通訊伺服器2003伺服器 API 撰寫的伺服器應用程式互動，可將其值設為 <STRONG>FALSE</STRONG>，以停用 BENOTIFY 要求。</span><span class="sxs-lookup"><span data-stu-id="3822f-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="3822f-322">BENOTIFY 目前不屬於 IETF (網際網路工程工作小組) SIP 標準化處理常式。</span><span class="sxs-lookup"><span data-stu-id="3822f-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="3822f-323">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-324">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-325">msRTCSIP-EnableFederation (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-326">此屬性是一種全域參數，由 IT 系統管理員用來設定是否允許使用者與其他組織的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3822f-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="3822f-327">它可讓系統管理員覆寫個別使用者的 <strong>FederationEnabled</strong> 屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="3822f-328">此屬性可用來協助保護內部網路免受來自公司的蠕蟲、病毒或目標攻擊可能造成的網際網路攻擊。</span><span class="sxs-lookup"><span data-stu-id="3822f-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="3822f-329">有效值 (和相關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-330">1：啟用公用 IM 連線 (位位置 0) </span><span class="sxs-lookup"><span data-stu-id="3822f-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="3822f-331">2：保留 (位位置 1) </span><span class="sxs-lookup"><span data-stu-id="3822f-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="3822f-332">4：保留 (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="3822f-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3822f-333">8：保留 (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="3822f-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="3822f-334">16：已啟用遠端呼叫控制 [電話語音] (位位置 4) </span><span class="sxs-lookup"><span data-stu-id="3822f-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="3822f-335">64： AllowOrganizeMeetingWithAnonymousParticipants (允許使用者邀請匿名使用者加入會議 (位位置 6) </span><span class="sxs-lookup"><span data-stu-id="3822f-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="3822f-336">128： UCEnabled (為使用者啟用整合通訊)  (位位置 7) </span><span class="sxs-lookup"><span data-stu-id="3822f-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="3822f-337">256： EnabledForEnhancedPresence (啟用使用者的公用 IM 連線)  (位位置 8) </span><span class="sxs-lookup"><span data-stu-id="3822f-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="3822f-338">512： RemoteCallControlDualMode (位位置 9) </span><span class="sxs-lookup"><span data-stu-id="3822f-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-339">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-340">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-341">msRTCSIP EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="3822f-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="3822f-342">此屬性會指出是否在指定的伺服器上載入企業服務。</span><span class="sxs-lookup"><span data-stu-id="3822f-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-343">msRTCSIP ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3822f-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="3822f-344">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-345">msRTCSIP ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="3822f-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="3822f-346">此屬性包含外部存取的撥號代碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="3822f-347">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-348">msRTCSIP FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="3822f-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="3822f-349">此屬性控制是否為單一使用者啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="3822f-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="3822f-350">它會由企業服務層強制執行。</span><span class="sxs-lookup"><span data-stu-id="3822f-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="3822f-351">它會標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="3822f-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3822f-352">有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-353">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="3822f-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="3822f-355">此屬性是與集區相關聯之所有 Enterprise Edition 伺服器的功能變數名稱的多重值清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="3822f-356">反向連結： <strong>連結 ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="3822f-357">此反向連結的對應正向連結是 <strong>msRTCSIP-PoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-358">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-359">msRTCSIP-Gateways (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-360">這個多重值字串屬性包含每個閘道)  (的閘道和埠清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="3822f-361">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-362">msRTCSIP-GlobalSettingsData (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-363">此屬性會儲存 [名稱：值] 配對。</span><span class="sxs-lookup"><span data-stu-id="3822f-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="3822f-364">已定義的 name： value 對適用于 <strong>允許輪詢顯示狀態</strong> 設定。</span><span class="sxs-lookup"><span data-stu-id="3822f-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="3822f-365">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="3822f-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="3822f-367">此屬性是群組的唯一識別碼，可用來群組通訊錄專案。</span><span class="sxs-lookup"><span data-stu-id="3822f-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="3822f-368">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-369">msRTCSIP-HomeServer (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-370">Live 通訊伺服器2003中的新增功能 (未使用) 。</span><span class="sxs-lookup"><span data-stu-id="3822f-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="3822f-371">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-372">msRTCSIP-HomeServerString (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-373">在即時通訊伺服器2003中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="3822f-374">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-375">msRTCSIP-HomeUsers (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-376">Live 通訊伺服器2003中的新增功能 (未使用) 。</span><span class="sxs-lookup"><span data-stu-id="3822f-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="3822f-377">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-378">msRTCSIP InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="3822f-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="3822f-379">此屬性控制是否單一使用者啟用外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="3822f-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="3822f-380">它會由企業服務層強制執行。</span><span class="sxs-lookup"><span data-stu-id="3822f-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="3822f-381">它會標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="3822f-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3822f-382">有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-383">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-384">msRTCSIP-IsMaster (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-385">即時通訊伺服器2003中的新功能</span><span class="sxs-lookup"><span data-stu-id="3822f-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="3822f-386">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-387">msRTCSIP 線</span><span class="sxs-lookup"><span data-stu-id="3822f-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="3822f-388">這個單一值屬性包含裝置識別碼 (使用者控制之電話的 SIP URI 或電話 URI，以供 Lync 用於電話語音) 使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="3822f-389">此屬性標示為進行通用類別目錄複寫，而且已編制索引。</span><span class="sxs-lookup"><span data-stu-id="3822f-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="3822f-390">如果使用者已啟用 Enterprise Voice，則此屬性會儲存為 e.164 的使用者電話號碼版本（164）。</span><span class="sxs-lookup"><span data-stu-id="3822f-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="3822f-391">Microsoft Office Live 通訊伺服器2005與 SP1 的新增功能</span><span class="sxs-lookup"><span data-stu-id="3822f-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-392">msRTCSIP LineServer</span><span class="sxs-lookup"><span data-stu-id="3822f-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="3822f-393">這個單一值屬性包含 CSTA-SIP 閘道伺服器的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="3822f-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="3822f-394">此屬性標示為通用類別目錄複寫，但沒有編制索引。</span><span class="sxs-lookup"><span data-stu-id="3822f-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="3822f-395">Microsoft Office Live 通訊伺服器2005與 SP1 的新增功能</span><span class="sxs-lookup"><span data-stu-id="3822f-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-396">msRTCSIP-LocalNormalizationData (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-397">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-398">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-399">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-400">msRTCSIP-LocalNormalizationLinks (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-401">此多重值屬性包含本機正規化辨別名稱的清單，這些名稱是 (DN) 與此位置設定檔相關聯。</span><span class="sxs-lookup"><span data-stu-id="3822f-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="3822f-402">此屬性的類型是 DN 二進位。</span><span class="sxs-lookup"><span data-stu-id="3822f-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="3822f-403">位置設定檔和本機正規化規則之間有一對多的關聯性。</span><span class="sxs-lookup"><span data-stu-id="3822f-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="3822f-404">本機正規化 DNs 清單的順序必須依管理員所指定的順序來維護。</span><span class="sxs-lookup"><span data-stu-id="3822f-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="3822f-405">順序保留是由 DN 二進位的二進位部分所維護，它會指定順序索引。</span><span class="sxs-lookup"><span data-stu-id="3822f-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="3822f-406">轉寄連結： <strong>連結 ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="3822f-407">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-LocationProfileBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-408">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-409">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-410">msRTCSIP LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="3822f-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="3822f-411">此屬性包含正常化規則的選項清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="3822f-412">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-413">msRTCSIP-LocationName (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-414">這個單一值屬性包含位置設定檔的易記名稱，表示此設定檔所代表的位置。</span><span class="sxs-lookup"><span data-stu-id="3822f-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="3822f-415">因為可以有多個位置設定檔，所以系統管理員需要一種方式來區分不同的設定檔。</span><span class="sxs-lookup"><span data-stu-id="3822f-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="3822f-416">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-417">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-418">msRTCSIP-locationProfileBL (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-419">此多重值屬性包含位置設定檔辨別名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="3822f-420">此屬性指定指向一或多個位置設定檔的後退連結。</span><span class="sxs-lookup"><span data-stu-id="3822f-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="3822f-421">反向連結： <strong>連結 ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="3822f-422">此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-LocalNormalizationLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-423">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-424">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-425">msRTCSIP-LocationProfileData (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-426">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-427">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-428">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-429">msRTCSIP LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="3822f-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="3822f-430">此屬性包含位置設定檔的選項。</span><span class="sxs-lookup"><span data-stu-id="3822f-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="3822f-431">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-432">msRTCSIP MappingContact</span><span class="sxs-lookup"><span data-stu-id="3822f-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="3822f-433">此多重值屬性包含應用程式連絡人的清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="3822f-434">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-435">msRTCSIP MappingLocation</span><span class="sxs-lookup"><span data-stu-id="3822f-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="3822f-436">此多重值屬性包含位置設定檔的清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="3822f-437">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-438">msRTCSIP-MaxNumOutstandingSearchPerServer (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-439">此屬性代表每個伺服器上的未完成搜尋要求數目上限。</span><span class="sxs-lookup"><span data-stu-id="3822f-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="3822f-440">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-441">msRTCSIP-MaxNumSubscriptionsPerUser (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-442">此屬性代表每位使用者的訂閱數目上限。</span><span class="sxs-lookup"><span data-stu-id="3822f-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="3822f-443">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-444">msRTCSIP-MaxPresenceSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-445">此屬性代表 [訂閱超時] 視窗的最大值。</span><span class="sxs-lookup"><span data-stu-id="3822f-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3822f-446">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-447">msRTCSIP-MaxRegistrationsTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-448">此屬性代表 [註冊超時] 視窗的最大值。</span><span class="sxs-lookup"><span data-stu-id="3822f-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3822f-449">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-451">此屬性代表最大的漫遊資料訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="3822f-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3822f-452">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-453">msRTCSIP MCUData</span><span class="sxs-lookup"><span data-stu-id="3822f-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="3822f-454">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-455">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="3822f-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="3822f-457">此屬性是電腦類別下的服務控制點屬性，可指定回其所屬的 multipoint 控制項單位 (MCU) 的連結。</span><span class="sxs-lookup"><span data-stu-id="3822f-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="3822f-458">這種服務控制點和屬性是針對每家 Microsoft MCU 而建立的。</span><span class="sxs-lookup"><span data-stu-id="3822f-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="3822f-459">每個 Microsoft MCU 都必須尋找所屬集區的後端伺服器，以便從該伺服器中取得集區層級設定。</span><span class="sxs-lookup"><span data-stu-id="3822f-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="3822f-460">此屬性的值是 MCU 工廠 (DN) 的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="3822f-461">這是單一值屬性，並標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="3822f-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3822f-462">轉寄連結： <strong>連結 ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="3822f-463">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-MCUServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-464">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-465">msRTCSIP MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="3822f-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="3822f-466">這是多字串保留屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="3822f-467">儲存在此屬性中的設定會以名稱 = 值一組來表示。</span><span class="sxs-lookup"><span data-stu-id="3822f-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="3822f-468">目前定義的 name = 值組為：</span><span class="sxs-lookup"><span data-stu-id="3822f-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-469">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="3822f-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-470">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="3822f-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="3822f-472">這是單一值屬性，包含與集區相關聯之單一 MCU 工廠 (DN) 的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="3822f-473">轉寄連結： <strong>連結 ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="3822f-474">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-PoolAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-475">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-476">msRTCSIP MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="3822f-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="3822f-477">此屬性是單一值字串，用來指定 MCU 工廠提供者的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3822f-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="3822f-478">根據 GUID 值，MCU 出廠過程會決定是否要為此 MCU 類型服務。</span><span class="sxs-lookup"><span data-stu-id="3822f-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="3822f-479">如果 GUID 值為 <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，則預設會在 Lync Server 中使用 MCU factory 程式 () 將會處理該流程。</span><span class="sxs-lookup"><span data-stu-id="3822f-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="3822f-480">對於任何其他 GUID 值，MCU 工廠處理常式將不會為 MCU 類型提供服務。</span><span class="sxs-lookup"><span data-stu-id="3822f-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="3822f-481">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="3822f-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="3822f-483">此屬性是多值的辨識名稱清單 (DN) 。</span><span class="sxs-lookup"><span data-stu-id="3822f-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="3822f-484">此屬性包含與這個 MCU 工廠相關聯之相同類型及廠商的所有 MCU 伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="3822f-485">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="3822f-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="3822f-486">反向連結：連結 ID 11027</span><span class="sxs-lookup"><span data-stu-id="3822f-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="3822f-487">此反向連結的對應正向連結是 <strong>msRTCSIP-MCUFactoryAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-488">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-489">msRTCSIP MCUType</span><span class="sxs-lookup"><span data-stu-id="3822f-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="3822f-490">此屬性是單一值字串，用來指定 MCU 可以處理的媒體。</span><span class="sxs-lookup"><span data-stu-id="3822f-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="3822f-491">支援的有效類型包括：</span><span class="sxs-lookup"><span data-stu-id="3822f-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-492">會議</span><span class="sxs-lookup"><span data-stu-id="3822f-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="3822f-493">音訊-影片</span><span class="sxs-lookup"><span data-stu-id="3822f-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="3822f-494">聊天</span><span class="sxs-lookup"><span data-stu-id="3822f-494">chat</span></span></p></li>
<li><p><span data-ttu-id="3822f-495">電話會議</span><span class="sxs-lookup"><span data-stu-id="3822f-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-496">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-497">msRTCSIP MCUVendor</span><span class="sxs-lookup"><span data-stu-id="3822f-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="3822f-498">此屬性是單一值字串，用來指定 MCU 廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="3822f-499">所有 Microsoft MCUs 都會將此屬性指定為 <strong>Microsoft Corporation</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-500">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-501">msRTCSIP-MeetingFlags (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-502">此屬性會定義針對所有使用者或連絡人物件全域啟用的不同會議選項。</span><span class="sxs-lookup"><span data-stu-id="3822f-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="3822f-503">此屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="3822f-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="3822f-504">有效值 (和相關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-505">0： AllowOrganizeMeetingWithAnonymousParticipants 為 None (不允許使用者邀請匿名使用者加入會議)  (未設定 bits) </span><span class="sxs-lookup"><span data-stu-id="3822f-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="3822f-506">4： AllowOrganizeMeetingWithAnonymousParticipants 每個人 (允許所有使用者邀請匿名使用者加入會議)  (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="3822f-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3822f-507">8： AllowOrganizeMeetingWithAnonymousParticipants UsePerUserSetting (允許使用者以每位使用者的使用者邀請匿名使用者為會議設定)  (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="3822f-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="3822f-508">16： UserPerUserMeetingPolicy (的會議原則是針對每位使用者定義)  (位位置 4) </span><span class="sxs-lookup"><span data-stu-id="3822f-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-509">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-510">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-511">msRTCSIP-MeetingPolicy (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-512">此屬性指定系統管理員為此使用者指派成單一值屬性的原則 (DN) 辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="3822f-513">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-514">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-515">msRTCSIP-MinPresenceSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-516">此屬性代表最小顯示狀態訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="3822f-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3822f-517">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-518">msRTCSIP-MinRegistrationTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-519">此屬性代表 [註冊超時] 視窗的最小值。</span><span class="sxs-lookup"><span data-stu-id="3822f-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3822f-520">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-521">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-523">此屬性代表最小的漫遊資料訂閱超時視窗。</span><span class="sxs-lookup"><span data-stu-id="3822f-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3822f-524">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-525">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-526">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="3822f-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="3822f-527">此屬性用來儲存前端集區所使用的鏡像 SQL Server 後端。</span><span class="sxs-lookup"><span data-stu-id="3822f-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="3822f-528">Lync Server 2013 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-529">msRTCSIP MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="3822f-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="3822f-530">此屬性包含定義行動性設定的選項和旗標。</span><span class="sxs-lookup"><span data-stu-id="3822f-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="3822f-531">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-532">msRTCSIP MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="3822f-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="3822f-533">此屬性包含行動性原則物件的 DN。</span><span class="sxs-lookup"><span data-stu-id="3822f-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="3822f-534">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-535">msRTCSIP-NumDevicesPerUser (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-536">此屬性代表允許的裝置數目，使用者可以在這些裝置上登錄 SIP 通訊並訂閱顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="3822f-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="3822f-537">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-538">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-539">msRTCSIP OptionFlags</span><span class="sxs-lookup"><span data-stu-id="3822f-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="3822f-540">此屬性會指定為 user 或 contact 物件啟用的選項。</span><span class="sxs-lookup"><span data-stu-id="3822f-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="3822f-541">此屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="3822f-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="3822f-542">每個選項都是以位表示。</span><span class="sxs-lookup"><span data-stu-id="3822f-542">Each option is represented by a bit.</span></span> <span data-ttu-id="3822f-543">此屬性標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="3822f-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3822f-544">有效值 (和相關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-545">1：啟用公用立即訊息 (IM) connectivity (位位置 0) </span><span class="sxs-lookup"><span data-stu-id="3822f-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="3822f-546">2：保留 (位位置 1) </span><span class="sxs-lookup"><span data-stu-id="3822f-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="3822f-547">4：保留 (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="3822f-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3822f-548">8：保留 (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="3822f-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="3822f-549">16：已啟用遠端呼叫控制 [電話語音] (位位置 4) </span><span class="sxs-lookup"><span data-stu-id="3822f-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="3822f-550">64： AllowOrganizeMeetingWithAnonymousParticipants (允許使用者邀請匿名使用者加入會議 (位位置 6) </span><span class="sxs-lookup"><span data-stu-id="3822f-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="3822f-551">128： UCEnabled (啟用使用者的 UC)  (位位置 7) </span><span class="sxs-lookup"><span data-stu-id="3822f-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="3822f-552">256： EnabledForEnhancedPresence (啟用使用者的公用 IM 連線)  (位位置 8) </span><span class="sxs-lookup"><span data-stu-id="3822f-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="3822f-553">512： RemoteCallControlDualMode (位位置 9) </span><span class="sxs-lookup"><span data-stu-id="3822f-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-554">使用 SP1 即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="3822f-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="3822f-556">在資源與中央樹系拓撲中，會使用此屬性來啟用單一登入時，當使用者從 Windows NT 伺服器主體帳戶 ObjectSID 至此屬性時，會將此屬性複製到資源或中央樹系中對應的使用者或連絡人物件的此屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="3822f-557">Communicator Web Access 使用此屬性或使用者的 ObjectSID 在 AD DS 中搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="3822f-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="3822f-558">此屬性標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="3822f-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-559">msRTCSIP OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="3822f-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="3822f-560">此屬性是應用程式連絡人擁有者的統一資源名稱 (URN) 。</span><span class="sxs-lookup"><span data-stu-id="3822f-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="3822f-561">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-562">msRTCSIP-Pattern (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-563">這個單一值字串屬性包含的模式，用來比對 e.164 格式的撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="3822f-564">如果撥號號碼符合此模式，就會將轉譯套用至撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="3822f-565">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-566">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-567">msRTCSIP-PhoneRouteBL (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-568">此多重值屬性包含電話路由辨別名稱 (DN) 清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="3822f-569">此屬性指定指向一或多個電話路由的反向連結。</span><span class="sxs-lookup"><span data-stu-id="3822f-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="3822f-570">反向連結： <strong>連結 ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="3822f-571">此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-RouteUsageLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-572">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-573">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-574">msRTCSIP-PhoneRouteData (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-575">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-576">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-577">msRTCSIP-PhoneRouteName (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-578">這個單一值的 UNICODE 字串屬性可指定電話路由的易記名稱，以便系統管理員輕易參考該名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="3822f-579">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-580">msRTCSIP-PhoneUsageData (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-581">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-582">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-583">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-584">msRTCSIP-PolicyContent (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-585">此屬性是單一值的 Unicode 字串。</span><span class="sxs-lookup"><span data-stu-id="3822f-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="3822f-586">這個字串屬性包含 XML 格式的原則定義。</span><span class="sxs-lookup"><span data-stu-id="3822f-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="3822f-587">XML 架構定義在不同的原則類型中是通用的，每個原則類型的設定值都各不相同。</span><span class="sxs-lookup"><span data-stu-id="3822f-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="3822f-588">XML 架構定義 (XSD) 定義如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="3822f-589">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-590">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-591">msRTCSIP-PolicyData (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-592">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-593">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-594">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-595">msRTCSIP-PolicyType (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-596">這個單一值的 Unicode 字串屬性包含原則類型。</span><span class="sxs-lookup"><span data-stu-id="3822f-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="3822f-597">有效的原則類型如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-598">會議</span><span class="sxs-lookup"><span data-stu-id="3822f-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="3822f-599">電話</span><span class="sxs-lookup"><span data-stu-id="3822f-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-600">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-601">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="3822f-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="3822f-603">此屬性指定的連結會傳回電腦所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="3822f-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="3822f-604">不論電腦正在執行 Standard Edition 還是 Lync Server Enterprise Edition，都設定此屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="3822f-605">此屬性標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="3822f-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3822f-606">有效的值是集區的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="3822f-607">轉寄連結： <strong>連結 ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="3822f-608">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-FrontEndServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-609">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="3822f-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="3822f-611">此多重值屬性包含與 MCU 工廠關聯之集區 (DN) 的辨識名稱清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="3822f-612">反向連結： <strong>連結 ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="3822f-613">此反向連結的對應正向連結是 <strong>msRTCSIP-MCUFactoryPath</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-614">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-615">msRTCSIP PoolData</span><span class="sxs-lookup"><span data-stu-id="3822f-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="3822f-616">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-617">使用 SP1 即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-618">msRTCSIP PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="3822f-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="3822f-619">此屬性會指定管理主控台所顯示集區的任意名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="3822f-620">系統管理員可以變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="3822f-621">有效的值是代表集區名稱的字串。</span><span class="sxs-lookup"><span data-stu-id="3822f-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="3822f-622">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-623">msRTCSIP PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="3822f-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="3822f-624">此屬性是單一值字串值。</span><span class="sxs-lookup"><span data-stu-id="3822f-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="3822f-625">當此屬性的值為時，如果系統管理員想要建立前端集區的 FQDN 不符合建立前端集區的 Active Directory 網域結構，則此屬性的值會代表集區的網域 FQDN (例如，SIP 命名空間會從網域名稱系統中脫離 (DNS) 命名空間) 。</span><span class="sxs-lookup"><span data-stu-id="3822f-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="3822f-626">建議您將前端集區域 FQDN 對應到功能變數名稱部分，以作為集區所在的 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="3822f-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="3822f-627">因此，當此屬性沒有任何值時，前端集區 FQDN 會預設為 Active Directory 功能變數名稱結構（由 <strong>dnsHostName</strong> 屬性工作表示）。</span><span class="sxs-lookup"><span data-stu-id="3822f-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="3822f-628">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-629">msRTCSIP PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="3822f-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="3822f-630">所有與集區相關聯之 Lync Server、Enterprise Edition Server 的功能變數名稱的多重值清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="3822f-631">Type integer 的此屬性可定義集區是否可以立即訊息 (IM) 和目前狀態，以及會議。</span><span class="sxs-lookup"><span data-stu-id="3822f-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="3822f-632">可能的有效值類型如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-633">未定義： IM 和目前狀態服務 (即時通訊伺服器2005和 2003) </span><span class="sxs-lookup"><span data-stu-id="3822f-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="3822f-634">1： IM 和目前狀態服務 (Lync Server) </span><span class="sxs-lookup"><span data-stu-id="3822f-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="3822f-635">2： IM 及目前狀態和會議服務 (Lync Server) </span><span class="sxs-lookup"><span data-stu-id="3822f-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-636">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-637">msRTCSIP PoolType</span><span class="sxs-lookup"><span data-stu-id="3822f-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="3822f-638">此屬性會指定伺服器集區是否正在執行 Standard Edition server 或 Enterprise Edition server。</span><span class="sxs-lookup"><span data-stu-id="3822f-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="3822f-639">此屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="3822f-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="3822f-640">每個選項都是以位表示。</span><span class="sxs-lookup"><span data-stu-id="3822f-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="3822f-641">有效值 (和相關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-642">1： Standard Edition server，主控使用者 (位位置 0) </span><span class="sxs-lookup"><span data-stu-id="3822f-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="3822f-643">2： Enterprise Edition 伺服器，主控使用者 (位位置 1) </span><span class="sxs-lookup"><span data-stu-id="3822f-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="3822f-644">4： Standard Edition server，主控應用程式 (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="3822f-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3822f-645">8： Enterprise Edition 伺服器，主控應用程式 (位位置 3) </span><span class="sxs-lookup"><span data-stu-id="3822f-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="3822f-646">因為 Lync Server 不支援僅裝載應用程式的集區，所以唯一有效的值如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-647">5： Standard Edition server，主控使用者和應用程式 (位位置0和 2) </span><span class="sxs-lookup"><span data-stu-id="3822f-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="3822f-648">10： Enterprise Edition 伺服器，主控使用者和應用程式 (位位置1和 3) </span><span class="sxs-lookup"><span data-stu-id="3822f-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-649">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-650">msRTCSIP PoolVersion</span><span class="sxs-lookup"><span data-stu-id="3822f-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="3822f-651">此屬性會定義集區的版本。</span><span class="sxs-lookup"><span data-stu-id="3822f-651">This attribute defines the pool version.</span></span> <span data-ttu-id="3822f-652">它是一種每一主要產品版本遞增的整數類型。</span><span class="sxs-lookup"><span data-stu-id="3822f-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="3822f-653">可能的有效值類型如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-654">0： Live 通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="3822f-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="3822f-655">1： Live 通訊伺服器2005</span><span class="sxs-lookup"><span data-stu-id="3822f-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="3822f-656">2： Live 通訊伺服器2005與 SP1</span><span class="sxs-lookup"><span data-stu-id="3822f-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="3822f-657">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="3822f-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="3822f-658">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3822f-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="3822f-659">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3822f-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-660">即時通訊伺服器2005與 SP1。</span><span class="sxs-lookup"><span data-stu-id="3822f-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-661">msRTCSIP PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="3822f-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="3822f-662">此屬性包含定義顯示狀態設定的選項和旗標。</span><span class="sxs-lookup"><span data-stu-id="3822f-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="3822f-663">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-664">msRTCSIP Microsoft.rtc.management.writableconfig.policy.presence.presencepolicy</span><span class="sxs-lookup"><span data-stu-id="3822f-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="3822f-665">此屬性包含目前狀態原則物件的 DN。</span><span class="sxs-lookup"><span data-stu-id="3822f-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="3822f-666">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="3822f-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="3822f-668">此屬性可讓使用者或連絡人進行 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="3822f-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="3822f-669">因為在中央樹系拓撲中，連絡人物件（而非使用者物件）已啟用 SIP，所以它會新增至連絡人類別。</span><span class="sxs-lookup"><span data-stu-id="3822f-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="3822f-670">有效值是使用者所在之 Standard Edition server 或 Enterprise Edition 前端集區的 DN。</span><span class="sxs-lookup"><span data-stu-id="3822f-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="3822f-671">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="3822f-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="3822f-673">此屬性包含指定使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="3822f-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="3822f-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="3822f-675">此屬性包含專用線路裝置的設備識別碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="3822f-676">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-677">msRTCSIP 路由</span><span class="sxs-lookup"><span data-stu-id="3822f-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="3822f-678">此屬性是 Boolean 屬性，用來判斷是否已授權 Lync Server 使用其 GRUU 位址路由傳送至此服務。</span><span class="sxs-lookup"><span data-stu-id="3822f-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="3822f-679">如果此值設為 <strong>TRUE</strong>，則會授權 Lync Server 路由傳送至此服務。</span><span class="sxs-lookup"><span data-stu-id="3822f-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="3822f-680">如果此值設為 <strong>FALSE</strong>，Lync Server 就不會獲得路由傳送到此服務的授權。</span><span class="sxs-lookup"><span data-stu-id="3822f-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="3822f-681">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-682">msRTCSIP-RouteUsageAttribute (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-683">這個單一值的 UNICODE 字串屬性定義的屬性會限定電話路由的使用方式。</span><span class="sxs-lookup"><span data-stu-id="3822f-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="3822f-684">電話路由的選取取決於兩個元素：指派給電話路由的使用方式屬性，以及來電者的允許原則使用屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="3822f-685">已選取具有與來電者允許之使用狀況屬性相符的第一個電話路由。</span><span class="sxs-lookup"><span data-stu-id="3822f-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="3822f-686">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-687">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-688">msRTCSIP-RouteUsageLinks (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-689">此多重值辨別名稱 (DN) 屬性包含路由流量辨別名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="3822f-690">轉寄連結： <strong>連結 ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="3822f-691">此屬性是對應的反向連結 <strong>msRTCSIP-PhoneRouteBL</strong>的向前連結。</span><span class="sxs-lookup"><span data-stu-id="3822f-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-692">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-693">msRTCSIP RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="3822f-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="3822f-694">此屬性包含 DN，該 DN 指向所有 SIP 流量定址至此 MCU 或受信任的服務必須經過的集區。</span><span class="sxs-lookup"><span data-stu-id="3822f-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="3822f-695">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-696">msRTCSIP-RuleName (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-697">這個單一值的 UNICODE 字串屬性會指定正規化規則的易記名稱，因此系統管理員可以輕易參考該名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="3822f-698">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-699">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="3822f-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="3822f-701">此屬性代表組織中目前部署的架構版本。</span><span class="sxs-lookup"><span data-stu-id="3822f-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-702">msRTCSIP-SearchMaxRequests (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-703">當使用者使用 Communicator 搜尋連絡人時，此屬性會限制目錄搜尋傳回的搜尋結果數目。</span><span class="sxs-lookup"><span data-stu-id="3822f-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="3822f-704">此屬性會覆寫用戶端提供的值。</span><span class="sxs-lookup"><span data-stu-id="3822f-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="3822f-705">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-706">msRTCSIP-SearchMaxResults (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-707">此屬性會限制傳回的搜尋要求數目。</span><span class="sxs-lookup"><span data-stu-id="3822f-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="3822f-708">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="3822f-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="3822f-710">此多重值屬性是一個 back 連結，其中包含可辨識名稱清單 (DN) 。</span><span class="sxs-lookup"><span data-stu-id="3822f-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="3822f-711">這些 DNs 指向集區或 <strong>TrustedService</strong> 物件。</span><span class="sxs-lookup"><span data-stu-id="3822f-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="3822f-712">此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-TrustedServiceLinks</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-713">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-714">msRTCSIP ServerData</span><span class="sxs-lookup"><span data-stu-id="3822f-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="3822f-715">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-716">msRTCSIP-ServerReferenceBL (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-717">此多重值屬性包含辨識名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="3822f-718">這些辨別名稱是指參照其他可指派預設位置設定檔之伺服器物件的連結。</span><span class="sxs-lookup"><span data-stu-id="3822f-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="3822f-719">反向連結： <strong>連結 ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="3822f-720">此反向連結的對應正向連結是 <strong>msRTCSIP-DefaultLocationProfileLink</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="3822f-721">此反向連結屬性只會參照集區和轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="3822f-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="3822f-722">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-723">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-724">msRTCSIP ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3822f-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="3822f-725">此屬性會定義伺服器的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="3822f-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="3822f-726">此版本編號適用于所有伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="3822f-726">This version number applies to all server roles.</span></span> <span data-ttu-id="3822f-727">它是隨每個官方產品發行增加的 monotonously 增加整數。</span><span class="sxs-lookup"><span data-stu-id="3822f-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="3822f-728">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-729">未定義： Live 通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="3822f-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="3822f-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="3822f-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="3822f-731">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="3822f-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="3822f-732">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="3822f-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="3822f-733">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3822f-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="3822f-734">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3822f-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="3822f-735">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3822f-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-736">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-737">msRTCSIP SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="3822f-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="3822f-738">整數類型的這個單一值屬性指定 <strong>msDS-SourceObjectDN</strong> 指向的物件類型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3822f-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-739">null |0x00000001：代表來自不同樹系的 Windows NT 伺服器主體使用者物件</span><span class="sxs-lookup"><span data-stu-id="3822f-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="3822f-740">下列屬性代表通訊群組擴充的不同樹系中的群組類型：</span><span class="sxs-lookup"><span data-stu-id="3822f-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-741">0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="3822f-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="3822f-742">0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="3822f-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="3822f-743">0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="3822f-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="3822f-744">0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="3822f-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="3822f-745">0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="3822f-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="3822f-746">0x90000000：代表來自相同樹系或不同樹系的自動語音應答或訂戶存取物件</span><span class="sxs-lookup"><span data-stu-id="3822f-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="3822f-747">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-748">msRTCSIP-SubscriptionAuthRequired (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-749">在即時通訊伺服器2003中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="3822f-750">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-751">msRTCSIP TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="3822f-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="3822f-752">此屬性可讓您將使用者或連絡人物件從一個 Lync 伺服器集區移至另一個。</span><span class="sxs-lookup"><span data-stu-id="3822f-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="3822f-753">此屬性會新增至連絡人類別，因為在中央樹系拓撲中，連絡人物件（而非使用者物件）已啟用 SIP。</span><span class="sxs-lookup"><span data-stu-id="3822f-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="3822f-754">有效值是要移動使用者之目的地 Standard Edition 伺服器或前端集區的 DN。</span><span class="sxs-lookup"><span data-stu-id="3822f-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="3822f-755">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-756">msRTCSIP-TargetPhoneNumber (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-757">這個單一值字串屬性包含電話號碼模式或範圍，以路由傳送至 <strong>msRTCSIP-Gateways</strong>中定義的指定閘道。</span><span class="sxs-lookup"><span data-stu-id="3822f-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-758">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-759">msRTCSIP TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="3822f-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="3822f-760">此屬性會儲存 Lync Server 使用者之目標原則的名稱-值對。</span><span class="sxs-lookup"><span data-stu-id="3822f-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="3822f-761">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-762">msRTCSIP TenantId</span><span class="sxs-lookup"><span data-stu-id="3822f-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="3822f-763">此屬性會儲存租使用者的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="3822f-764">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-765">msRTCSIP-Translation (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-766">此屬性是 Lync Server 的語音功能使用的，且包含翻譯字串以套用至撥號號碼（如果找到相符的號碼）。</span><span class="sxs-lookup"><span data-stu-id="3822f-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="3822f-767">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3822f-768">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-769">msRTCSIP TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="3822f-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="3822f-770">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-771">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-772">msRTCSIP TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="3822f-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="3822f-773">此屬性是包含 MCU FQDN 的字串值。</span><span class="sxs-lookup"><span data-stu-id="3822f-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="3822f-774">這是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-774">This is a single-valued attribute.</span></span> <span data-ttu-id="3822f-775">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="3822f-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3822f-776">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-777">msRTCSIP TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="3822f-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="3822f-778">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-779">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-780">msRTCSIP TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="3822f-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="3822f-781">此屬性是包含執行 Proxy 伺服器之伺服器的 FQDN 的字串值。</span><span class="sxs-lookup"><span data-stu-id="3822f-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="3822f-782">此屬性是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-782">This attribute is single-valued.</span></span> <span data-ttu-id="3822f-783">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="3822f-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3822f-784">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-785">msRTCSIP TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="3822f-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="3822f-786">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-787">msRTCSIP TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="3822f-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="3822f-788">此屬性是單一值屬性，代表受信任伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3822f-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="3822f-789">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-790">msRTCSIP TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="3822f-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="3822f-791">此屬性會指定受信任的伺服器清單中伺服器的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="3822f-792">可能的有效值如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-793">Null： Live 通訊伺服器2003</span><span class="sxs-lookup"><span data-stu-id="3822f-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="3822f-794">2： Live 通訊伺服器2005</span><span class="sxs-lookup"><span data-stu-id="3822f-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="3822f-795">3： Office 通訊伺服器2007</span><span class="sxs-lookup"><span data-stu-id="3822f-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="3822f-796">4： Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3822f-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="3822f-797">5： Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3822f-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="3822f-798">6： Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3822f-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-799">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-800">msRTCSIP TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="3822f-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="3822f-801">此屬性會定義為受信任的服務啟用的選項。</span><span class="sxs-lookup"><span data-stu-id="3822f-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="3822f-802">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="3822f-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="3822f-804">此多重值屬性包含辨識名稱清單 (DN) 參考信任的服務物件，例如媒體轉送驗證服務。</span><span class="sxs-lookup"><span data-stu-id="3822f-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="3822f-805">執行 A/V 會議服務之 Edge Server 上的媒體轉送驗證服務 (實際組合) 必須與集區相關聯，以支援遠端使用者的音訊案例。</span><span class="sxs-lookup"><span data-stu-id="3822f-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="3822f-806">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-ServerBL</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-807">Uc</span><span class="sxs-lookup"><span data-stu-id="3822f-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-808">msRTCSIP TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="3822f-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="3822f-809">此屬性是一個整數，用來定義用來連線到此 GRUU 服務的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="3822f-810">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-811">msRTCSIP TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="3822f-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="3822f-812">此屬性是定義其所代表之 GRUU 服務類型的字串值。</span><span class="sxs-lookup"><span data-stu-id="3822f-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="3822f-813">有效的 GRUU 服務類型如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="3822f-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="3822f-815">閘道</span><span class="sxs-lookup"><span data-stu-id="3822f-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="3822f-816">媒體轉送驗證服務 (MRAS) </span><span class="sxs-lookup"><span data-stu-id="3822f-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="3822f-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="3822f-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="3822f-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="3822f-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-819">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-820">msRTCSIP TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="3822f-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="3822f-821">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-822">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-823">msRTCSIP TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="3822f-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="3822f-824">此屬性是包含執行 Lync Server Web 服務之 IIS 之 FQDN 的字串值。</span><span class="sxs-lookup"><span data-stu-id="3822f-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="3822f-825">這是單一值屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-825">This is a single-valued attribute.</span></span> <span data-ttu-id="3822f-826">每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</span><span class="sxs-lookup"><span data-stu-id="3822f-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3822f-827">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-828">msRTCSIP-UCFlags (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-829">此屬性定義不同的 UC 選項，可供全域對所有的使用者或連絡人物件啟用。</span><span class="sxs-lookup"><span data-stu-id="3822f-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="3822f-830">此屬性是整數類型的位元遮罩值。</span><span class="sxs-lookup"><span data-stu-id="3822f-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="3822f-831">每個選項都是以一位的狀態來表示。</span><span class="sxs-lookup"><span data-stu-id="3822f-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="3822f-832">可能有效的值 (和關聯的位位置) 如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-833">4： UsePerUserUCPolicy (位位置 2) </span><span class="sxs-lookup"><span data-stu-id="3822f-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="3822f-834">設定此位時，即會定義每位使用者的 UC 原則。</span><span class="sxs-lookup"><span data-stu-id="3822f-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="3822f-835">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-836">msRTCSIP-UCPolicy (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-837">這個單一值屬性包含系統管理員為此使用者指派的 UC 原則 (DN) 辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="3822f-838">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-839">msRTCSIP-UserDomainList (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3822f-840">此屬性提供樹系中所有主控 SIP-enabled 使用者的網域清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="3822f-841">預設值為空白清單，表示樹系中的所有網域都已 SIP-enabled。</span><span class="sxs-lookup"><span data-stu-id="3822f-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="3822f-842">有效的值為多個字串，代表個別網域的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="3822f-843">在即時通訊伺服器2005中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3822f-844">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="3822f-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="3822f-846">此屬性會決定使用者目前是否已啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="3822f-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-847">msRTCSIP UserExtension</span><span class="sxs-lookup"><span data-stu-id="3822f-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="3822f-848">此多重值屬性以 name = value 的格式包含名稱-值對的清單 &quot; 。 &quot; 此屬性標示為進行通用類別目錄複寫。</span><span class="sxs-lookup"><span data-stu-id="3822f-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="3822f-849">使用 SP1 即時通訊伺服器2005中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-850">msRTCSIP UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="3822f-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="3822f-851">此屬性包含指向位置設定檔物件 (DN) 的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="3822f-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="3822f-852">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-853">msRTCSIP UserPolicies</span><span class="sxs-lookup"><span data-stu-id="3822f-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="3822f-854">此屬性儲存使用者原則的名稱-值對。</span><span class="sxs-lookup"><span data-stu-id="3822f-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="3822f-855">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-856">msRTCSIP UserPolicy</span><span class="sxs-lookup"><span data-stu-id="3822f-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="3822f-857">這是多重值屬性，包含具有二進位 (DN_WITH_BINARY) 指向全域使用者原則的不同類型的辨識名稱清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="3822f-858">二進位部分會指出 DN 部分指向的原則類型。</span><span class="sxs-lookup"><span data-stu-id="3822f-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="3822f-859">有效的二進位值如下：</span><span class="sxs-lookup"><span data-stu-id="3822f-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-860">0x00000001：會議原則</span><span class="sxs-lookup"><span data-stu-id="3822f-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="3822f-861">0x00000002： UC 原則</span><span class="sxs-lookup"><span data-stu-id="3822f-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="3822f-862">0x00000005：顯示狀態原則</span><span class="sxs-lookup"><span data-stu-id="3822f-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-863">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-864">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="3822f-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="3822f-865">這是 SIP 路由群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="3822f-866">相同群組中的使用者會註冊到同一個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="3822f-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="3822f-867">Lync Server 2013 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-868">msRTCSIP WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="3822f-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="3822f-869">這是多重值屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="3822f-870">此屬性保留供日後使用。</span><span class="sxs-lookup"><span data-stu-id="3822f-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3822f-871">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="3822f-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="3822f-873">這個單一值屬性會指向網頁元件所屬的集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="3822f-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="3822f-874">轉寄連結： <strong>連結 ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="3822f-875">此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-WebComponentsServers</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-876">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="3822f-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="3822f-878">此屬性是多重值的辨識名稱清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="3822f-879">此屬性包含與此集區相關聯之所有網頁伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="3822f-880">反向連結： <strong>連結 ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="3822f-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="3822f-881">此反向連結的對應正向連結是 <strong>msRTCSIP-WebComponentsPoolAddress</strong>。</span><span class="sxs-lookup"><span data-stu-id="3822f-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3822f-882">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-883">msRTCSIP-WMIInstanceId (過時) </span><span class="sxs-lookup"><span data-stu-id="3822f-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3822f-884">在即時通訊伺服器2003中新增。</span><span class="sxs-lookup"><span data-stu-id="3822f-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="3822f-885">在即時通訊伺服器2005中已過時。</span><span class="sxs-lookup"><span data-stu-id="3822f-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="3822f-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="3822f-887">電話語音會使用這個現有的 Active Directory 屬性來指定電話的備用 TCP/IP 地址清單。</span><span class="sxs-lookup"><span data-stu-id="3822f-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="3822f-888">Windows Server 2008 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="3822f-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="3822f-890">Lync Server 中的語音元件會使用這個現有的 Active Directory 屬性，針對連絡人物件，以供路由呼叫至整合通訊自動語音應答和使用者存取號碼的目的。</span><span class="sxs-lookup"><span data-stu-id="3822f-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="3822f-891">無條件呼叫轉寄位址會儲存在此多重值屬性中。</span><span class="sxs-lookup"><span data-stu-id="3822f-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="3822f-892">此帳戶是針對自動語音應答和使用者存取的特定用途而建立。</span><span class="sxs-lookup"><span data-stu-id="3822f-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="3822f-893">管理員不應修改這個帳戶的屬性。</span><span class="sxs-lookup"><span data-stu-id="3822f-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="3822f-894">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3822f-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3822f-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3822f-896">這個現有的 Active Directory 多重值屬性是 Windows 2000 中所引進之基礎 Active Directory 架構的一部分。</span><span class="sxs-lookup"><span data-stu-id="3822f-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="3822f-897">此屬性包含使用者電子郵件的各種 X400、X500 及 SMTP 位址。</span><span class="sxs-lookup"><span data-stu-id="3822f-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="3822f-898">在即時通訊伺服器2003和更新版本中，會使用 [sip：] 標記將使用者的 SIP URI 新增至此清單 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="3822f-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="3822f-899">下列應用程式會從此屬性搜尋使用者的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="3822f-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="3822f-900">Microsoft Office Outlook 2003 訊息與共同作業用戶端</span><span class="sxs-lookup"><span data-stu-id="3822f-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="3822f-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="3822f-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3822f-902">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3822f-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="3822f-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="3822f-904">這個現有的 Active Directory 屬性包含使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3822f-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="3822f-905">Windows 2000 作業系統中的新功能。</span><span class="sxs-lookup"><span data-stu-id="3822f-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

