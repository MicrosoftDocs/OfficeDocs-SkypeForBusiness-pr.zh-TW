---
title: Lync Server 2013：安裝 Lync for Windows Phone
description: Lync Server 2013：安裝 Lync for Windows Phone。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573979"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="79a8b-103">在 Lync Server 2013 中安裝 Lync for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="79a8b-103">Installing Lync for Windows Phone in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79a8b-104">_**主題上次修改日期：** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="79a8b-104">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="79a8b-105">適用于 Windows Phone 的 Lync 2013 是一種可供使用者安裝的應用程式，可在 Windows Phone Marketplace 中使用。</span><span class="sxs-lookup"><span data-stu-id="79a8b-105">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="79a8b-106">安裝 Lync for Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="79a8b-106">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="79a8b-107">您可以透過導向使用者至 Windows Phone Marketplace，指示您的使用者在其裝置上安裝 Lync 2013 for Windows Phone <https://go.microsoft.com/fwlink/p/?linkid=231901> 。</span><span class="sxs-lookup"><span data-stu-id="79a8b-107">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <https://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="79a8b-108">如果您使用 DNS SRV 記錄發佈 Exchange Web 服務</span><span class="sxs-lookup"><span data-stu-id="79a8b-108">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="79a8b-109">為了啟用 Lync 用戶端的 Exchange 整合，有些組織會使用 DNS SRV 記錄發佈 Exchange Web 服務 URL。</span><span class="sxs-lookup"><span data-stu-id="79a8b-109">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="79a8b-110">Microsoft 下載中心提供的檔「瞭解及疑難排解 Exchange 整合」， [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) 會說明可能需要這種情況的案例。</span><span class="sxs-lookup"><span data-stu-id="79a8b-110">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="79a8b-111">不過，在此案例中，Windows Phone 使用者的 Exchange 整合不會運作，因為 Windows Phone 平臺不支援 SRV 查閱。</span><span class="sxs-lookup"><span data-stu-id="79a8b-111">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="79a8b-112">您必須指示 Windows Phone 使用者指定 Exchange Web 服務 URL，而不是讓電話自動偵測到伺服器。</span><span class="sxs-lookup"><span data-stu-id="79a8b-112">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="79a8b-113">指示您的使用者在其 Windows 電話上設定 Lync 設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="79a8b-113">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="79a8b-114">在 [Windows Phone] 的 [Lync 設定] 中，選取 [ **Exchange** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="79a8b-114">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="79a8b-115">將 **自動偵測伺服器** 移至 **關閉狀態**。</span><span class="sxs-lookup"><span data-stu-id="79a8b-115">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="79a8b-116">點擊空白欄位，並輸入 Exchange Web 服務 (FQDN) 或 URL 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="79a8b-116">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79a8b-117">您可以指定完整功能變數名稱 (FQDN) 或您的 Exchange Web 服務伺服器的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="79a8b-117">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="79a8b-118">如果您指定 FQDN，通訊協定 (HTTPs://) ，且會自動新增 Exchange Web 服務路徑 (/ews/exchange.asmx) 。</span><span class="sxs-lookup"><span data-stu-id="79a8b-118">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="79a8b-119">如果您的 Exchange Web 服務路徑不同，您可以指定完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="79a8b-119">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="79a8b-120">關閉螢幕。</span><span class="sxs-lookup"><span data-stu-id="79a8b-120">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="79a8b-121">確認行動用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="79a8b-121">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="79a8b-122">在您設定用戶端並登入成功之後，請使用下列測試來確認您的 Lync 2013 安裝在行動裝置上是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="79a8b-122">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="79a8b-123">**在公司目錄中搜尋連絡人**</span><span class="sxs-lookup"><span data-stu-id="79a8b-123">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="79a8b-124">在 [連絡人] 清單中，按一下底部的 [ **搜尋** ]。</span><span class="sxs-lookup"><span data-stu-id="79a8b-124">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="79a8b-125">搜尋只存在於全域通訊清單中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="79a8b-125">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="79a8b-126">確認連絡人名稱出現在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="79a8b-126">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="79a8b-127">**測試立即訊息和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="79a8b-127">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="79a8b-128">在 [連絡人] 清單中，按一下連絡人。</span><span class="sxs-lookup"><span data-stu-id="79a8b-128">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="79a8b-129">在連絡人卡片中，按一下 [ **IM** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="79a8b-129">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="79a8b-130">確認立即訊息 (IM) ] 視窗隨即出現，而且您可以輸入及傳送 IM。</span><span class="sxs-lookup"><span data-stu-id="79a8b-130">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="79a8b-131">**測試電話撥出式會議**</span><span class="sxs-lookup"><span data-stu-id="79a8b-131">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="79a8b-132">在 Outlook 中，排程 Lync 會議。</span><span class="sxs-lookup"><span data-stu-id="79a8b-132">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="79a8b-133">在行動裝置上，開啟會議邀請。</span><span class="sxs-lookup"><span data-stu-id="79a8b-133">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="79a8b-134">按一下會議中的連結以加入。</span><span class="sxs-lookup"><span data-stu-id="79a8b-134">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="79a8b-135">從會議服務接聽來電，並確認您已連線至會議音訊。</span><span class="sxs-lookup"><span data-stu-id="79a8b-135">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="79a8b-136">**測試推播通知**</span><span class="sxs-lookup"><span data-stu-id="79a8b-136">**Test push notifications**</span></span>

1.  <span data-ttu-id="79a8b-137">在使用者 A 的行動裝置上，使用使用者 A 的帳戶登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="79a8b-137">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="79a8b-138">在行動裝置上開啟另一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="79a8b-138">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="79a8b-139">在不同的用戶端上，使用使用者 B 的帳戶登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="79a8b-139">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="79a8b-140">從使用者 B 傳送 IM 給使用者 A。</span><span class="sxs-lookup"><span data-stu-id="79a8b-140">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="79a8b-141">確認 IM 通知出現在使用者 A 的行動裝置上。</span><span class="sxs-lookup"><span data-stu-id="79a8b-141">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

