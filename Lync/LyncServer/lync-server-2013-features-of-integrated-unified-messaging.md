---
title: Lync Server 2013：整合式 Unified Messaging 的功能
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
ms.openlocfilehash: 69726c614df344c76b06cf68e4d844c0514af7dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="28895-102">整合式 Unified Messaging 和 Lync Server 2013 的功能</span><span class="sxs-lookup"><span data-stu-id="28895-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28895-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="28895-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="28895-104">Lync Server 2013，企業語音使用 Exchange 整合通訊（UM）基礎結構來提供通話應答、呼叫通知、語音存取（包括語音信箱）及自動助理服務。</span><span class="sxs-lookup"><span data-stu-id="28895-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="28895-105">呼叫應答</span><span class="sxs-lookup"><span data-stu-id="28895-105">Call Answering</span></span>

<span data-ttu-id="28895-106">[通話接聽] 是代表不接聽或忙碌通話的使用者接收語音訊息。</span><span class="sxs-lookup"><span data-stu-id="28895-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="28895-107">它包括播放個人問候語、記錄郵件，以及提交郵件以傳送到使用者的信箱，而該信箱會儲存在 Exchange 信箱伺服器上。</span><span class="sxs-lookup"><span data-stu-id="28895-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="28895-108">如果來電者離開郵件，郵件會傳送到使用者的 [收件匣]。</span><span class="sxs-lookup"><span data-stu-id="28895-108">If a caller leaves a message, the message is routed to the user's Inbox.</span></span> <span data-ttu-id="28895-109">如果來電者選擇不留下訊息，就會將未接來電通知儲存在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="28895-109">If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox.</span></span> <span data-ttu-id="28895-110">然後，使用者就可以使用 Microsoft Outlook 的訊息與共同作業用戶端、Outlook Web Access、Exchange ActiveSync 技術或 Outlook 語音存取來存取收件匣。</span><span class="sxs-lookup"><span data-stu-id="28895-110">Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access.</span></span> <span data-ttu-id="28895-111">通話的主旨與優先順序可以以與電子郵件類似的方式顯示。</span><span class="sxs-lookup"><span data-stu-id="28895-111">The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="28895-112">Outlook 語音存取</span><span class="sxs-lookup"><span data-stu-id="28895-112">Outlook Voice Access</span></span>

<span data-ttu-id="28895-113">Outlook 語音存取可讓企業語音使用者存取除語音信箱以外的 [Exchange 收件匣]，包括來自電話介面的電子郵件、行事曆和連絡人。</span><span class="sxs-lookup"><span data-stu-id="28895-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="28895-114">訂閱者存取號碼是由 Exchange UM 管理員指派。</span><span class="sxs-lookup"><span data-stu-id="28895-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="28895-115">自動語音應答</span><span class="sxs-lookup"><span data-stu-id="28895-115">Auto Attendant</span></span>

<span data-ttu-id="28895-116">自動語音應答是一種 Exchange UM 功能，可讓您用來設定使用者可以撥打電話給公司代表的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="28895-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="28895-117">特別是，它提供一系列的語音提示，協助外部呼叫者流覽功能表系統。</span><span class="sxs-lookup"><span data-stu-id="28895-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="28895-118">可用選項的清單是由 Exchange UM 管理員在 Exchange UM 伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="28895-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="28895-119">傳真服務</span><span class="sxs-lookup"><span data-stu-id="28895-119">Fax Services</span></span>

<span data-ttu-id="28895-120">Exchange UM 包括 [傳真] 功能，可讓使用者在其 Exchange 信箱中接收傳入的傳真。</span><span class="sxs-lookup"><span data-stu-id="28895-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="28895-121">如需詳細資訊，請參閱 Microsoft Exchange Server 檔中的「整合[http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)訊息」。</span><span class="sxs-lookup"><span data-stu-id="28895-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28895-122">Exchange UM 伺服器提供的傳真服務無法在與 Microsoft Exchange Server 2010、Exchange 2010 （含最新 service pack 或 Exchange 2013）整合的 Lync Server 部署中使用。</span><span class="sxs-lookup"><span data-stu-id="28895-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

