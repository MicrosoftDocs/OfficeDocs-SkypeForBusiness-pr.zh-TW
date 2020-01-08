---
title: Lync Server 2013：安裝 Lync for Windows Phone
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeb8f43ea4f4db15a9a057bd0d7b24c55d858cb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="b204d-102">在 Lync Server 2013 中安裝 Lync for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b204d-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b204d-103">_**主題上次修改日期：** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="b204d-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="b204d-104">Windows Phone 適用的 Lync 2013 是 Windows Phone Marketplace 提供的使用者可安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="b204d-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="b204d-105">安裝 Lync for Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="b204d-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="b204d-106">您可以透過將 Lync 2013 的裝置導向至 Windows Phone Marketplace，來指示您的使用者在他們的裝置上<http://go.microsoft.com/fwlink/p/?linkid=231901>安裝 Lync For windows phone。</span><span class="sxs-lookup"><span data-stu-id="b204d-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="b204d-107">如果您使用 DNS SRV 記錄發佈 Exchange Web 服務</span><span class="sxs-lookup"><span data-stu-id="b204d-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="b204d-108">若要啟用 Lync 用戶端的 Exchange 整合，有些組織會使用 DNS SRV 記錄來發佈 Exchange Web 服務 URL。</span><span class="sxs-lookup"><span data-stu-id="b204d-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="b204d-109">Microsoft 下載中心提供的檔「瞭解及疑難排解 Exchange 整合」 [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)，說明可能需要進行的案例。</span><span class="sxs-lookup"><span data-stu-id="b204d-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="b204d-110">不過，Windows phone 版 Exchange 整合使用者無法在這種情況下運作，因為 Windows Phone 平臺不支援 SRV 查閱。</span><span class="sxs-lookup"><span data-stu-id="b204d-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="b204d-111">您將需要指示 Windows Phone 使用者指定 Exchange Web 服務 URL，而不是允許手機自動偵測伺服器。</span><span class="sxs-lookup"><span data-stu-id="b204d-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="b204d-112">指示您的使用者在其 Windows 手機上設定 Lync 設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b204d-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="b204d-113">在 Windows Phone 的 Lync 設定中，選取 [ **Exchange** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="b204d-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="b204d-114">將 [**自動偵測伺服器**] 移至 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="b204d-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="b204d-115">敲擊空白欄位，然後輸入 Exchange Web 服務的完整功能變數名稱（FQDN）或 URL。</span><span class="sxs-lookup"><span data-stu-id="b204d-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b204d-116">您可以指定 Exchange Web 服務伺服器的完整功能變數名稱（FQDN）或完整 URL。</span><span class="sxs-lookup"><span data-stu-id="b204d-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="b204d-117">如果您指定 FQDN，就會自動新增通訊協定（HTTPs://）和 Exchange Web 服務路徑（/ews/exchange.asmx）。</span><span class="sxs-lookup"><span data-stu-id="b204d-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="b204d-118">如果 Exchange Web 服務路徑不一樣，您可以指定完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="b204d-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="b204d-119">關閉螢幕。</span><span class="sxs-lookup"><span data-stu-id="b204d-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="b204d-120">驗證行動用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="b204d-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="b204d-121">在您設定用戶端並成功登入之後，請使用下列測試確認您的 Lync 2013 安裝在您的行動裝置上正常運作。</span><span class="sxs-lookup"><span data-stu-id="b204d-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="b204d-122">**在公司目錄中搜尋連絡人**</span><span class="sxs-lookup"><span data-stu-id="b204d-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="b204d-123">在 [連絡人] 清單中，按一下底部的 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="b204d-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="b204d-124">搜尋僅存在於全域通訊清單中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="b204d-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="b204d-125">確認連絡人名稱出現在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="b204d-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="b204d-126">**測試立即訊息和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="b204d-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="b204d-127">在連絡人清單中，輕觸連絡人。</span><span class="sxs-lookup"><span data-stu-id="b204d-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="b204d-128">在連絡人卡片中，按一下 [ **IM** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="b204d-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="b204d-129">確認立即訊息（IM）視窗出現，而且您可以輸入並傳送即時消息。</span><span class="sxs-lookup"><span data-stu-id="b204d-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="b204d-130">**測試撥出式會議**</span><span class="sxs-lookup"><span data-stu-id="b204d-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="b204d-131">在 Outlook 中，排程 Lync 會議。</span><span class="sxs-lookup"><span data-stu-id="b204d-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="b204d-132">在行動裝置上，開啟會議邀請。</span><span class="sxs-lookup"><span data-stu-id="b204d-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="b204d-133">按一下會議中要加入的連結。</span><span class="sxs-lookup"><span data-stu-id="b204d-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="b204d-134">從會議服務接聽通話，並確認您已連線到會議音訊。</span><span class="sxs-lookup"><span data-stu-id="b204d-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="b204d-135">**測試推播通知**</span><span class="sxs-lookup"><span data-stu-id="b204d-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="b204d-136">在使用者 A 的行動裝置上，使用使用者 A 的帳戶登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="b204d-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="b204d-137">在行動裝置上開啟另一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="b204d-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="b204d-138">在其他用戶端上，使用使用者 B 的帳戶登入 Lync。</span><span class="sxs-lookup"><span data-stu-id="b204d-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="b204d-139">從使用者 B 傳送 IM 給使用者 A。</span><span class="sxs-lookup"><span data-stu-id="b204d-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="b204d-140">確認 IM 通知出現在使用者 A 的行動裝置上。</span><span class="sxs-lookup"><span data-stu-id="b204d-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

