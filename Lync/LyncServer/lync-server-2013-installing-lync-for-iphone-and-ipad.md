---
title: Lync Server 2013：安裝 Lync for iPhone 和 iPad 版
description: Lync Server 2013：安裝 Lync for iPhone 和 iPad。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for iPhone and iPad
ms:assetid: 88d1c149-5842-4ecf-a15e-fcda0330325b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690987(v=OCS.15)
ms:contentKeyID: 51541496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b186cca023d7d65146f3f9c91149c49a5555de81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573969"
---
# <a name="installing-lync-for-iphone-and-ipad-in-lync-server-2013"></a><span data-ttu-id="f230d-103">在 Lync Server 2013 中安裝 Lync for iPhone 和 iPad</span><span class="sxs-lookup"><span data-stu-id="f230d-103">Installing Lync for iPhone and iPad in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f230d-104">_**主題上次修改日期：** 2014-03-10_</span><span class="sxs-lookup"><span data-stu-id="f230d-104">_**Topic Last Modified:** 2014-03-10_</span></span>

<span data-ttu-id="f230d-105">Lync 2013 for iPhone 和 Lync 2013 for iPad 是可供使用者安裝的應用程式，可在 Apple 應用程式存放區中使用。</span><span class="sxs-lookup"><span data-stu-id="f230d-105">Lync 2013 for iPhone and Lync 2013 for iPad are user-installable applications that are available in the Apple App Store.</span></span>

<div>

## <a name="installing-lync-for-iphone-and-lync-for-ipad"></a><span data-ttu-id="f230d-106">安裝 Lync for iPhone 和 Lync for iPad</span><span class="sxs-lookup"><span data-stu-id="f230d-106">Installing Lync for iPhone and Lync for iPad</span></span>

<span data-ttu-id="f230d-107">您可以指示您的使用者安裝 Lync 2013 for iPhone 和 Lync 2013 for iPad，方法是將其導向裝置中的應用程式存放區。</span><span class="sxs-lookup"><span data-stu-id="f230d-107">You can instruct your users to install Lync 2013 for iPhone and Lync 2013 for iPad by directing them to the App Store from their devices.</span></span> <span data-ttu-id="f230d-108">您也可以在線上使用每個裝置的應用程式存放區。</span><span class="sxs-lookup"><span data-stu-id="f230d-108">The App Store for each device is also available online.</span></span>

  - <span data-ttu-id="f230d-109">Lync for iPhone 可在 ttp://www.apple.com/iphone/from-the-app-store/的應用程式存放區中取得 \< h<span> </span> ></span><span class="sxs-lookup"><span data-stu-id="f230d-109">Lync for iPhone is available in the App Store at \< h<span></span>ttp://www.apple.com/iphone/from-the-app-store/></span></span>

  - <span data-ttu-id="f230d-110">Lync for iPad 可在 tp://www.apple.com/ipad/from-the-app-store/的應用程式存放區中取得 \< ht<span> </span> ></span><span class="sxs-lookup"><span data-stu-id="f230d-110">Lync for iPad is available in the App Store at \< ht<span></span>tp://www.apple.com/ipad/from-the-app-store/></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f230d-111">尚未安裝 Lync 2013 應用程式的 iPhone 使用者，以及嘗試加入來自會議邀請之 Lync 會議的使用者，將會重新導向至 [加入啟動器] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f230d-111">iPhone users who have not installed the Lync 2013 app and who try to join a Lync meeting from a meeting invitation will be redirected to a Join Launcher page.</span></span> <span data-ttu-id="f230d-112">此頁面包含安裝 Lync 2013 應用程式的連結。</span><span class="sxs-lookup"><span data-stu-id="f230d-112">This page contains a link for installing the Lync 2013 app.</span></span> <span data-ttu-id="f230d-113">不過，此連結會開啟空白的 Safari 瀏覽器頁面，而不是將使用者導向至應用程式存放區。</span><span class="sxs-lookup"><span data-stu-id="f230d-113">However, instead of directing the user to the App Store, this link opens a blank Safari browser page.</span></span> <span data-ttu-id="f230d-114">使用者可以執行下列兩項操作以解決此問題：</span><span class="sxs-lookup"><span data-stu-id="f230d-114">The user can do one of two things to work around this issue:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="f230d-115">使用 [ <STRONG>主</STRONG> ] 按鈕，將 safari 頁面傳送至背景，然後重新開啟 safari。</span><span class="sxs-lookup"><span data-stu-id="f230d-115">Use the <STRONG>Home</STRONG> button to send the Safari page to the background, and then reopen Safari.</span></span> <span data-ttu-id="f230d-116">出現 [在應用程式存放區中開啟此頁面] 的通知時，按一下 [ <STRONG>開啟</STRONG> ]，即可將其導向至應用程式存放區中的 Lync 2013 下載。</span><span class="sxs-lookup"><span data-stu-id="f230d-116">When the notification “Open this page in App Store” appears, tap <STRONG>Open</STRONG> to be directed to Lync 2013 download in the App Store.</span></span></P>
> <LI>
> <P><span data-ttu-id="f230d-117">手動開啟應用程式存放區，搜尋 "Lync 2013"，然後下載應用程式。</span><span class="sxs-lookup"><span data-stu-id="f230d-117">Manually open the App Store, search for "Lync 2013," and download the app.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="f230d-118">確認行動用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="f230d-118">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="f230d-119">在您設定用戶端並登入成功之後，請使用下列測試來確認您的 Lync 安裝在行動裝置上正常運作。</span><span class="sxs-lookup"><span data-stu-id="f230d-119">After you configure the client and sign in successfully, use the following tests to verify that your Lync installation is working correctly on your mobile device.</span></span>

<span data-ttu-id="f230d-120">**在公司目錄中搜尋連絡人**</span><span class="sxs-lookup"><span data-stu-id="f230d-120">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="f230d-121">在 [連絡人] 清單中，依序按一下上方的搜尋列，然後開始輸入只存在於全域通訊清單 (GAL) 中的連絡人名稱。</span><span class="sxs-lookup"><span data-stu-id="f230d-121">In the Contacts list, tap inside the search bar at the top, and begin typing the name of a contact that exists only in the global address list (GAL).</span></span>

2.  <span data-ttu-id="f230d-122">確認連絡人名稱出現在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="f230d-122">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="f230d-123">**測試立即訊息和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="f230d-123">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="f230d-124">在 [連絡人] 清單中，按一下連絡人。</span><span class="sxs-lookup"><span data-stu-id="f230d-124">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="f230d-125">在連絡人卡片中，按一下 [ **IM** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="f230d-125">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="f230d-126">確認立即訊息 (IM) ] 視窗隨即出現，而且您可以輸入及傳送 IM。</span><span class="sxs-lookup"><span data-stu-id="f230d-126">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="f230d-127">**測試電話撥出式會議**</span><span class="sxs-lookup"><span data-stu-id="f230d-127">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="f230d-128">在 Outlook 中，排程 Lync 會議。</span><span class="sxs-lookup"><span data-stu-id="f230d-128">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="f230d-129">在行動裝置上，開啟會議邀請。</span><span class="sxs-lookup"><span data-stu-id="f230d-129">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="f230d-130">按一下會議中的連結以加入。</span><span class="sxs-lookup"><span data-stu-id="f230d-130">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="f230d-131">從會議服務接聽來電，並確認您已連線至會議音訊。</span><span class="sxs-lookup"><span data-stu-id="f230d-131">Answer the call from the conference service and verify that you are connected to the meeting audio.</span></span>

<span data-ttu-id="f230d-132">**測試推播通知**</span><span class="sxs-lookup"><span data-stu-id="f230d-132">**Test push notifications**</span></span>

1.  <span data-ttu-id="f230d-133">在使用者 A 的行動裝置上，使用使用者 A 的帳戶登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="f230d-133">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="f230d-134">在行動裝置上開啟另一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="f230d-134">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="f230d-135">在不同的用戶端上，使用使用者 B 的帳戶登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="f230d-135">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="f230d-136">從使用者 B 傳送 IM 給使用者 A。</span><span class="sxs-lookup"><span data-stu-id="f230d-136">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="f230d-137">確認 IM 通知出現在使用者 A 的行動裝置上。</span><span class="sxs-lookup"><span data-stu-id="f230d-137">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

