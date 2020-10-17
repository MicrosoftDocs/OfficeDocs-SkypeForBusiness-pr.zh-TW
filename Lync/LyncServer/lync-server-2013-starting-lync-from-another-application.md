---
title: Lync Server 2013：從其他應用程式啟動 Lync
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
ms.openlocfilehash: 0d10e70615083796baa0934c6291b377dcd18005
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519510"
---
# <a name="starting-lync-from-another-application"></a><span data-ttu-id="32380-102">從另一個應用程式啟動 Lync</span><span class="sxs-lookup"><span data-stu-id="32380-102">Starting Lync from another application</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32380-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="32380-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="32380-104">您可以使用命令列參數，快速地啟動 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="32380-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="32380-105">例如，如果使用者按一下另一個應用程式中的電話號碼，應用程式就可以啟動 Lync 2013 的實例，並初始化對該號碼的呼叫。</span><span class="sxs-lookup"><span data-stu-id="32380-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="32380-106">Lync 2013 也可以辨識以分號分隔的連絡人名稱清單，以供多方會議使用。</span><span class="sxs-lookup"><span data-stu-id="32380-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="32380-107">如果 Lync 2013 已設定為在開始時自動登入，則使用命令列參數啟動 Lync 2013 時，會開啟 Lync 主視窗。</span><span class="sxs-lookup"><span data-stu-id="32380-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="32380-108">若 Lync 未設定為在開始時自動登入，則會開啟登入視窗。</span><span class="sxs-lookup"><span data-stu-id="32380-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="32380-109">下表顯示可用的參數。</span><span class="sxs-lookup"><span data-stu-id="32380-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="32380-110">Lync 2013 Command-Line 參數</span><span class="sxs-lookup"><span data-stu-id="32380-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32380-111">副檔名</span><span class="sxs-lookup"><span data-stu-id="32380-111">Extension</span></span></th>
<th><span data-ttu-id="32380-112">資料格式</span><span class="sxs-lookup"><span data-stu-id="32380-112">Format of Data</span></span></th>
<th><span data-ttu-id="32380-113">動作</span><span class="sxs-lookup"><span data-stu-id="32380-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32380-114">電話：</span><span class="sxs-lookup"><span data-stu-id="32380-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="32380-115">電話 URI</span><span class="sxs-lookup"><span data-stu-id="32380-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="32380-116">會開啟語音通話的交談視窗，但不會撥打指定的號碼。</span><span class="sxs-lookup"><span data-stu-id="32380-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32380-117">callto</span><span class="sxs-lookup"><span data-stu-id="32380-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="32380-118">電話：、sip：或 typeable 電話 URI</span><span class="sxs-lookup"><span data-stu-id="32380-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="32380-119">會開啟語音通話的交談視窗，但不會撥打指定的號碼。</span><span class="sxs-lookup"><span data-stu-id="32380-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32380-120">Sip：</span><span class="sxs-lookup"><span data-stu-id="32380-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="32380-121">SIP URI</span><span class="sxs-lookup"><span data-stu-id="32380-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="32380-122">在參與者清單中，以指定的 SIP 統一資源識別項 (URI) 開啟 [交談] 視窗。</span><span class="sxs-lookup"><span data-stu-id="32380-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32380-123">Sip</span><span class="sxs-lookup"><span data-stu-id="32380-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="32380-124">SIP URI</span><span class="sxs-lookup"><span data-stu-id="32380-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="32380-125">如果 Lync 2013 設定為使用傳輸層安全性 (TLS) 通訊協定，其功能與 sip 完全相同：。</span><span class="sxs-lookup"><span data-stu-id="32380-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="32380-126">若未使用 TLS，會顯示一個對話方塊，告知使用者需要較高的安全性層級。</span><span class="sxs-lookup"><span data-stu-id="32380-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32380-127">會議</span><span class="sxs-lookup"><span data-stu-id="32380-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="32380-128">加入會議的 SIP URI</span><span class="sxs-lookup"><span data-stu-id="32380-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="32380-129">如果 URI 是自我，請將焦點具現化，並只顯示僅限名單的模式。</span><span class="sxs-lookup"><span data-stu-id="32380-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="32380-130">否則，會顯示名單視圖，但不會傳送邀請。</span><span class="sxs-lookup"><span data-stu-id="32380-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32380-131">我：</span><span class="sxs-lookup"><span data-stu-id="32380-131">im:</span></span></p></td>
<td><p><span data-ttu-id="32380-132">SIP URI</span><span class="sxs-lookup"><span data-stu-id="32380-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="32380-133">以 SIP URI 顯示立即訊息 (IM) 專用交談視窗。</span><span class="sxs-lookup"><span data-stu-id="32380-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="32380-134">接受在 &lt; &gt; 不含任何分隔符號 () 中的角括弧中指定的多個 SIP URIs。</span><span class="sxs-lookup"><span data-stu-id="32380-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32380-135">下表提供這些命令列參數的範例。</span><span class="sxs-lookup"><span data-stu-id="32380-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="32380-136">Command-Line 參數範例</span><span class="sxs-lookup"><span data-stu-id="32380-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32380-137">Instance</span><span class="sxs-lookup"><span data-stu-id="32380-137">Instance</span></span></th>
<th><span data-ttu-id="32380-138">結果</span><span class="sxs-lookup"><span data-stu-id="32380-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32380-139">電話： + 14255550101</span><span class="sxs-lookup"><span data-stu-id="32380-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="32380-140">開啟具有 + 14255550101 的僅限電話的視圖。</span><span class="sxs-lookup"><span data-stu-id="32380-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32380-141">Callto：電話： + 14255550101</span><span class="sxs-lookup"><span data-stu-id="32380-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="32380-142">開啟具有 + 14255550101 的僅限電話的視圖。</span><span class="sxs-lookup"><span data-stu-id="32380-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32380-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="32380-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="32380-144">使用 kazuto@litwareinc.com 開啟僅限電話的視圖。</span><span class="sxs-lookup"><span data-stu-id="32380-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32380-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="32380-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="32380-146">使用 kazuto@litwareinc.com 開啟交談視窗。</span><span class="sxs-lookup"><span data-stu-id="32380-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32380-147">會議： sip：https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="32380-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="32380-148">開啟 [交談] 視窗並顯示會議音訊加入選項。</span><span class="sxs-lookup"><span data-stu-id="32380-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

