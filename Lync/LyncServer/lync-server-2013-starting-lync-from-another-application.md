---
title: Lync Server 2013： 從另一個應用程式啟動 Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e7a48645301b6c822eed52ea31e6d4b46019bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="9bc43-102">從另一個應用程式啟動 Lync</span><span class="sxs-lookup"><span data-stu-id="9bc43-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bc43-103">_**上次修改主題：** 2013年-02-20 個_</span><span class="sxs-lookup"><span data-stu-id="9bc43-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9bc43-104">您可以使用命令列參數，以快速開始 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="9bc43-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="9bc43-105">例如，如果使用者按一下 [其他應用程式中的電話號碼，應用程式可以啟動 Lync 2013 的執行個體，並啟動該號碼。</span><span class="sxs-lookup"><span data-stu-id="9bc43-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="9bc43-106">Lync 2013 還能辨識分號分隔的連絡人名稱清單以便進行多方會議。</span><span class="sxs-lookup"><span data-stu-id="9bc43-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="9bc43-107">若 Lync 2013 設為自動啟動時，登入，然後以命令列參數啟動 Lync 2013 將會開啟在 Lync 主視窗。</span><span class="sxs-lookup"><span data-stu-id="9bc43-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="9bc43-108">如果 Lync 未設定成在啟動時，會自動登入，登入視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="9bc43-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="9bc43-109">下表顯示可用的參數。</span><span class="sxs-lookup"><span data-stu-id="9bc43-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="9bc43-110">Lync 2013 命令列參數</span><span class="sxs-lookup"><span data-stu-id="9bc43-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bc43-111">副檔名</span><span class="sxs-lookup"><span data-stu-id="9bc43-111">Extension</span></span></th>
<th><span data-ttu-id="9bc43-112">資料格式</span><span class="sxs-lookup"><span data-stu-id="9bc43-112">Format of Data</span></span></th>
<th><span data-ttu-id="9bc43-113">動作</span><span class="sxs-lookup"><span data-stu-id="9bc43-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bc43-114">tel:</span><span class="sxs-lookup"><span data-stu-id="9bc43-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="9bc43-115">tel URI</span><span class="sxs-lookup"><span data-stu-id="9bc43-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="9bc43-116">開啟音訊通話的 [交談] 視窗，但不會撥打指定的號碼。</span><span class="sxs-lookup"><span data-stu-id="9bc43-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc43-117">callto:</span><span class="sxs-lookup"><span data-stu-id="9bc43-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="9bc43-118">tel:，sip:，或可輸入的 tel URI</span><span class="sxs-lookup"><span data-stu-id="9bc43-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="9bc43-119">開啟音訊通話的 [交談] 視窗，但不會撥打指定的號碼。</span><span class="sxs-lookup"><span data-stu-id="9bc43-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc43-120">sip:</span><span class="sxs-lookup"><span data-stu-id="9bc43-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="9bc43-121">SIP URI</span><span class="sxs-lookup"><span data-stu-id="9bc43-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="9bc43-122">開啟 「 交談 」 視窗與指定之 SIP 統一資源識別元 (URI) 在參與者清單中。</span><span class="sxs-lookup"><span data-stu-id="9bc43-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc43-123">Sips:</span><span class="sxs-lookup"><span data-stu-id="9bc43-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="9bc43-124">SIP URI</span><span class="sxs-lookup"><span data-stu-id="9bc43-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="9bc43-125">如果 Lync 2013 設定為使用傳輸層安全性 (TLS) 通訊協定，函式完全像 sip:。</span><span class="sxs-lookup"><span data-stu-id="9bc43-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="9bc43-126">如果未使用 TLS，會顯示對話方塊，告知使用者的安全性層級必要。</span><span class="sxs-lookup"><span data-stu-id="9bc43-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc43-127">conf:</span><span class="sxs-lookup"><span data-stu-id="9bc43-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="9bc43-128">SIP URI 的會議加入</span><span class="sxs-lookup"><span data-stu-id="9bc43-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="9bc43-129">如果 self URI，具現化焦點，並會帶出名冊僅限檢視。</span><span class="sxs-lookup"><span data-stu-id="9bc43-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="9bc43-130">否則，會帶出名冊檢視，但不會傳送邀請。</span><span class="sxs-lookup"><span data-stu-id="9bc43-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc43-131">im:</span><span class="sxs-lookup"><span data-stu-id="9bc43-131">im:</span></span></p></td>
<td><p><span data-ttu-id="9bc43-132">SIP URI</span><span class="sxs-lookup"><span data-stu-id="9bc43-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="9bc43-133">會顯示 [立即訊息 (IM)-僅交談視窗與 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="9bc43-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="9bc43-134">可接受多個 SIP Uri 指定內角括弧 (&lt;&gt;) 不含任何分隔符號。</span><span class="sxs-lookup"><span data-stu-id="9bc43-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9bc43-135">下表提供上述命令列參數範例。</span><span class="sxs-lookup"><span data-stu-id="9bc43-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="9bc43-136">命令列參數範例</span><span class="sxs-lookup"><span data-stu-id="9bc43-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bc43-137">執行個體</span><span class="sxs-lookup"><span data-stu-id="9bc43-137">Instance</span></span></th>
<th><span data-ttu-id="9bc43-138">結果</span><span class="sxs-lookup"><span data-stu-id="9bc43-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bc43-139">Tel: 14255550101</span><span class="sxs-lookup"><span data-stu-id="9bc43-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="9bc43-140">會開啟 14255550101 的僅限電話檢視。</span><span class="sxs-lookup"><span data-stu-id="9bc43-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc43-141">Callto:tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="9bc43-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="9bc43-142">會開啟 14255550101 的僅限電話檢視。</span><span class="sxs-lookup"><span data-stu-id="9bc43-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc43-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9bc43-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="9bc43-144">開啟內含 kazuto@litwareinc.com 的僅限電話檢視。</span><span class="sxs-lookup"><span data-stu-id="9bc43-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc43-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9bc43-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="9bc43-146">開啟內含 kazuto@litwareinc.com 的交談視窗。</span><span class="sxs-lookup"><span data-stu-id="9bc43-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc43-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="9bc43-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="9bc43-148">開啟的交談視窗並顯示會議音訊加入選項。</span><span class="sxs-lookup"><span data-stu-id="9bc43-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

