---
title: Lync Server 2013：從另一個應用程式啟動 Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="0b7e4-102">從另一個應用程式啟動 Lync</span><span class="sxs-lookup"><span data-stu-id="0b7e4-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b7e4-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="0b7e4-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="0b7e4-104">您可以使用命令列參數快速啟動 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="0b7e4-105">例如，如果使用者在其他應用程式中按一下電話號碼，應用程式可以啟動 Lync 2013 的實例，並初始化該號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="0b7e4-106">Lync 2013 也可以辨識以分號分隔的多方會議連絡人名稱清單。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="0b7e4-107">如果 Lync 2013 已設定為在啟動時自動登入，則使用命令列參數啟動 Lync 2013，就會開啟 Lync 主視窗。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="0b7e4-108">如果 Lync 未設定為在啟動時自動登入，[登入] 視窗就會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="0b7e4-109">下表顯示可用的參數。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="0b7e4-110">Lync 2013 命令列參數</span><span class="sxs-lookup"><span data-stu-id="0b7e4-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b7e4-111">延伸</span><span class="sxs-lookup"><span data-stu-id="0b7e4-111">Extension</span></span></th>
<th><span data-ttu-id="0b7e4-112">資料的格式</span><span class="sxs-lookup"><span data-stu-id="0b7e4-112">Format of Data</span></span></th>
<th><span data-ttu-id="0b7e4-113">動作</span><span class="sxs-lookup"><span data-stu-id="0b7e4-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b7e4-114">tel</span><span class="sxs-lookup"><span data-stu-id="0b7e4-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-115">電話 URI</span><span class="sxs-lookup"><span data-stu-id="0b7e4-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-116">開啟 [交談] 視窗以進行音訊通話，但不會撥打指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b7e4-117">callto</span><span class="sxs-lookup"><span data-stu-id="0b7e4-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-118">電話：，sip：，或 typeable 電話 URI</span><span class="sxs-lookup"><span data-stu-id="0b7e4-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-119">開啟 [交談] 視窗以進行音訊通話，但不會撥打指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b7e4-120">呼吸</span><span class="sxs-lookup"><span data-stu-id="0b7e4-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-121">SIP URI</span><span class="sxs-lookup"><span data-stu-id="0b7e4-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-122">在參與者清單中，開啟含有指定 SIP 統一資源識別項（URI）的 [交談] 視窗。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b7e4-123">那些</span><span class="sxs-lookup"><span data-stu-id="0b7e4-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-124">SIP URI</span><span class="sxs-lookup"><span data-stu-id="0b7e4-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-125">如果 Lync 2013 設定為使用傳輸層安全性（TLS）通訊協定，則功能與 sip 完全一樣：。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="0b7e4-126">如果沒有使用 TLS，則會顯示一個對話方塊，通知使用者需要較高的安全性等級。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b7e4-127">會議</span><span class="sxs-lookup"><span data-stu-id="0b7e4-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-128">加入會議的 SIP URI</span><span class="sxs-lookup"><span data-stu-id="0b7e4-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-129">如果 URI 是 self，請將焦點放在一起，並顯示 [僅限名單] 視圖。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="0b7e4-130">否則，會顯示 [名單] 視圖，但不會傳送邀請。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b7e4-131">傳遞</span><span class="sxs-lookup"><span data-stu-id="0b7e4-131">im:</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-132">SIP URI</span><span class="sxs-lookup"><span data-stu-id="0b7e4-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-133">顯示含有 SIP URI 的立即訊息（IM）專用交談視窗。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="0b7e4-134">接受在不含任何分隔符號的角括弧（&lt;&gt;）內指定的多個 SIP uri。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0b7e4-135">下表提供這些命令列參數的範例。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="0b7e4-136">命令列參數範例</span><span class="sxs-lookup"><span data-stu-id="0b7e4-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b7e4-137">示例</span><span class="sxs-lookup"><span data-stu-id="0b7e4-137">Instance</span></span></th>
<th><span data-ttu-id="0b7e4-138">這樣</span><span class="sxs-lookup"><span data-stu-id="0b7e4-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b7e4-139">電話： + 14255550101</span><span class="sxs-lookup"><span data-stu-id="0b7e4-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-140">開啟只有 [+ 14255550101] 的 [僅限手機] 視圖。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b7e4-141">Callto：電話： + 14255550101</span><span class="sxs-lookup"><span data-stu-id="0b7e4-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-142">開啟只有 [+ 14255550101] 的 [僅限手機] 視圖。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b7e4-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b7e4-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-144">開啟 [僅限手機] 視圖，並顯示 kazuto@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b7e4-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b7e4-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-146">使用 kazuto@litwareinc.com 開啟交談視窗。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b7e4-147">會議： sip：https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="0b7e4-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="0b7e4-148">開啟交談視窗，並顯示會議音訊連接選項。</span><span class="sxs-lookup"><span data-stu-id="0b7e4-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

