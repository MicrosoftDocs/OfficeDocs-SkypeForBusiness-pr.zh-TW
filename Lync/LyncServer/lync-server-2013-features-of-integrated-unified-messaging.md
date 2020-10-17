---
title: Lync Server 2013：整合式整合通訊的功能
description: Lync Server 2013：整合式整合通訊的功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2caa75504c0468293ced8f20946500fad7cf54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543399"
---
# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="cd960-103">整合整合通訊和 Lync Server 2013 的功能</span><span class="sxs-lookup"><span data-stu-id="cd960-103">Features of integrated Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd960-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cd960-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cd960-105">Lync Server 2013，Enterprise Voice 使用 Exchange 整合通訊 (UM) 基礎結構，提供通話回應、來電通知、語音存取 (包括語音信箱) 和自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="cd960-105">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="cd960-106">來電接聽</span><span class="sxs-lookup"><span data-stu-id="cd960-106">Call Answering</span></span>

<span data-ttu-id="cd960-107">呼叫應答是代表使用者接收語音訊息，但來電並未接聽或占線。</span><span class="sxs-lookup"><span data-stu-id="cd960-107">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="cd960-108">它包含播放個人問候語、錄製郵件，並將郵件送出佇列以傳送至使用者的信箱，該信箱儲存在 Exchange 信箱伺服器上。</span><span class="sxs-lookup"><span data-stu-id="cd960-108">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="cd960-p102">如果來電者留下訊息，該訊息就會傳送到使用者的收件匣。如果來電者選擇不留下任何訊息，則會在使用者的信箱中儲存未接來電通知。然後使用者可以使用 Microsoft Outlook 訊息和共同作業用戶端、Outlook Web Access、Exchange ActiveSync 技術或 Outlook Voice Access 存取自己的收件匣。可以使用與電子郵件類似的方式來顯示來電的主旨和優先順序。</span><span class="sxs-lookup"><span data-stu-id="cd960-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="cd960-113">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="cd960-113">Outlook Voice Access</span></span>

<span data-ttu-id="cd960-114">Outlook Voice Access 不只可讓企業語音使用者從電話語音介面存取語音信箱，還可以存取 Exchange 收件匣，其中包括電子郵件、行事曆和連絡人。</span><span class="sxs-lookup"><span data-stu-id="cd960-114">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="cd960-115">「使用者存取號碼」是由 Exchange UM 管理員所指派。</span><span class="sxs-lookup"><span data-stu-id="cd960-115">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="cd960-116">自動語音應答</span><span class="sxs-lookup"><span data-stu-id="cd960-116">Auto Attendant</span></span>

<span data-ttu-id="cd960-117">自動語音應答是一種 Exchange UM 功能，可用來設定使用者可以撥出的電話號碼，以到達公司代表。</span><span class="sxs-lookup"><span data-stu-id="cd960-117">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="cd960-118">特別是，它提供了一系列的語音提示，可協助外部來電者瀏覽功能表系統。</span><span class="sxs-lookup"><span data-stu-id="cd960-118">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="cd960-119">[可用選項] 清單是由 Exchange um 管理員在 Exchange UM 伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="cd960-119">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="cd960-120">傳真服務</span><span class="sxs-lookup"><span data-stu-id="cd960-120">Fax Services</span></span>

<span data-ttu-id="cd960-121">Exchange UM 包含傳真功能，可讓使用者在其 Exchange 信箱中接收傳入的傳真。</span><span class="sxs-lookup"><span data-stu-id="cd960-121">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="cd960-122">如需詳細資訊，請參閱《 Microsoft Exchange Server 檔》中的「整合通訊」 [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652) 。</span><span class="sxs-lookup"><span data-stu-id="cd960-122">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd960-123">Exchange UM 伺服器所提供的傳真服務無法在與 Microsoft Exchange Server 2010、Exchange 2010 及最新 service pack 或 Exchange 2013 整合的 Lync Server 部署中使用。</span><span class="sxs-lookup"><span data-stu-id="cd960-123">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

