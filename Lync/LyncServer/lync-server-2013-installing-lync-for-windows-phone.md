---
title: Lync Server 2013： 安裝 Lync for Windows Phone
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
ms.openlocfilehash: e2dcb2b1fdc41d1d4dd9a047eceaba8bcbc2c3ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="25147-102">安裝 Lync for Lync Server 2013 中的 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="25147-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25147-103">_**上次修改主題：** 2014年-02-03_</span><span class="sxs-lookup"><span data-stu-id="25147-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="25147-104">Lync 2013 for Windows Phone 是 Windows Phone 市集處於可用的使用者安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="25147-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="25147-105">安裝 Lync for Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="25147-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="25147-106">您可以指示使用者導向至 Windows Phone 市集其裝置上安裝 Lync 2013 for Windows Phone <https://go.microsoft.com/fwlink/p/?linkid=231901>。</span><span class="sxs-lookup"><span data-stu-id="25147-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <https://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="25147-107">如果您使用 DNS SRV 記錄來發佈 Exchange Web 服務</span><span class="sxs-lookup"><span data-stu-id="25147-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="25147-108">若要啟用 Exchange 整合的 Lync 用戶端，有些組織會使用 DNS SRV 記錄來發佈 Exchange Web 服務 URL。</span><span class="sxs-lookup"><span data-stu-id="25147-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="25147-109">文件 」 了解和疑難排解 Exchange 整合，「 Microsoft 下載中心提供[https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095)，描述在其中這可能需要的案例。</span><span class="sxs-lookup"><span data-stu-id="25147-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="25147-110">不過，Exchange 整合的 Windows Phone 使用者將無法運作在此案例中，因為在 Windows Phone 平台不支援 SRV 查閱。</span><span class="sxs-lookup"><span data-stu-id="25147-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="25147-111">您將需要指示 Windows Phone 使用者指定的 Exchange Web 服務 URL 而不讓電話會自動偵測到伺服器。</span><span class="sxs-lookup"><span data-stu-id="25147-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="25147-112">指示使用者在其 Windows Phone 上設定 Lync 設定如下：</span><span class="sxs-lookup"><span data-stu-id="25147-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="25147-113">在 Windows Phone Lync 設定中，選取 [ **Exchange** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="25147-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="25147-114">將**自動偵測伺服器**移至**關閉**。</span><span class="sxs-lookup"><span data-stu-id="25147-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="25147-115">點選 [空白欄位，然後輸入完整的網域名稱 (FQDN) 或 Exchange Web 服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="25147-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25147-116">您可以指定完整的網域名稱 (FQDN) 或 Exchange Web 服務伺服器的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="25147-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="25147-117">如果您指定的 FQDN、 通訊協定 (https://) 和 Exchange Web 服務路徑 (/ ews/exchange.asmx) 會自動加入。</span><span class="sxs-lookup"><span data-stu-id="25147-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="25147-118">如果您的 Exchange Web 服務路徑不同，您可以指定完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="25147-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="25147-119">關閉 [] 畫面。</span><span class="sxs-lookup"><span data-stu-id="25147-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="25147-120">確認行動用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="25147-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="25147-121">設定用戶端並登入成功之後，使用下列測試來確認 Lync 2013 的安裝行動裝置上正確運作。</span><span class="sxs-lookup"><span data-stu-id="25147-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="25147-122">**搜尋在公司目錄中的連絡人**</span><span class="sxs-lookup"><span data-stu-id="25147-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="25147-123">在 [連絡人] 清單中，點選 [底部的 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="25147-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="25147-124">搜尋只存在於全域通訊清單的連絡人。</span><span class="sxs-lookup"><span data-stu-id="25147-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="25147-125">確認連絡人名稱出現在搜尋結果中。</span><span class="sxs-lookup"><span data-stu-id="25147-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="25147-126">**測試 im 和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="25147-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="25147-127">在 [連絡人] 清單中，點選 [連絡人]。</span><span class="sxs-lookup"><span data-stu-id="25147-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="25147-128">連絡人卡片中點選**IM**圖示。</span><span class="sxs-lookup"><span data-stu-id="25147-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="25147-129">請確認立即訊息 (IM) 視窗隨即出現，而且您可以輸入及傳送 IM。</span><span class="sxs-lookup"><span data-stu-id="25147-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="25147-130">**測試電話撥出式會議**</span><span class="sxs-lookup"><span data-stu-id="25147-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="25147-131">在 Outlook 中，排程 Lync 會議。</span><span class="sxs-lookup"><span data-stu-id="25147-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="25147-132">在行動裝置上，開啟會議邀請。</span><span class="sxs-lookup"><span data-stu-id="25147-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="25147-133">按一下會議中的連結以加入。</span><span class="sxs-lookup"><span data-stu-id="25147-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="25147-134">從會議服務接聽來電，並確認您已連線至會議音訊。</span><span class="sxs-lookup"><span data-stu-id="25147-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="25147-135">**測試推入通知**</span><span class="sxs-lookup"><span data-stu-id="25147-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="25147-136">在使用者 A 的行動裝置上登入 Lync 使用者 A 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="25147-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="25147-137">開啟 [行動裝置上的另一個應用程式]。</span><span class="sxs-lookup"><span data-stu-id="25147-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="25147-138">在不同的用戶端上登入 Lync 使用者 B 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="25147-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="25147-139">從使用者 B 傳送 IM 給使用者 a。</span><span class="sxs-lookup"><span data-stu-id="25147-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="25147-140">確認 IM 通知出現在使用者 A 的行動裝置上。</span><span class="sxs-lookup"><span data-stu-id="25147-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

