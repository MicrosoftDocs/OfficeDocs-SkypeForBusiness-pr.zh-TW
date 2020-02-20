---
title: Lync Server 2013： 特色與功能的前端伺服器、 立即訊息和目前狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 639df8bdcee7531895eaafe9dd8ca5fac3f6fc3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="324c9-102">前端伺服器、 立即訊息和 Lync Server 2013 中的目前狀態的功能</span><span class="sxs-lookup"><span data-stu-id="324c9-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="324c9-103">_**上次修改主題：** 2013年-03-17_</span><span class="sxs-lookup"><span data-stu-id="324c9-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="324c9-104">前端伺服器提供大部分的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="324c9-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="324c9-105">有可用的兩種版本： Lync Server Enterprise Edition，主要針對較大型的組織，這和 Lync Server Standard Edition，其設計主要是針對較小的組織想較小的硬體 investement 並不是需要高可用性。</span><span class="sxs-lookup"><span data-stu-id="324c9-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="324c9-106">這兩個版本支援包括 IM、 目前狀態、 會議及 Enterprise Voice 的所有 Lync 伺服器工作負載。</span><span class="sxs-lookup"><span data-stu-id="324c9-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="324c9-p102">立即訊息 (IM) 可讓使用者在電腦上使用文字訊息，與其他使用者進行即時溝通。同時支援雙方或多方 IM 工作階段。雙方 IM 交談中的參與者可以隨時將第三個參與者加入交談中。若發生這種情況，[交談] 視窗會變更成可支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="324c9-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="324c9-111">Lync 及 Communicator 用戶端時參與一對一的通訊，通常稱為端對端。</span><span class="sxs-lookup"><span data-stu-id="324c9-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="324c9-112">技術上而言，兩個用戶端進行通訊與立即訊息 multipoint 控制項中的單位 (IMMCU) 中間的一對一交談中。</span><span class="sxs-lookup"><span data-stu-id="324c9-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="324c9-113">IMMCU 是前端伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="324c9-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="324c9-114">必要的通訊工作流程中放置 IMMCU 可讓詳細通話記錄及其他功能，可讓前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="324c9-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="324c9-115">前端伺服器連接埠 TLS/TCP/5061 （假設使用建議的傳輸層安全性） 是從用戶端上動態來源連接埠通訊。</span><span class="sxs-lookup"><span data-stu-id="324c9-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="324c9-116">根據設計，端對端通訊 （以及多方 IM） 時，可能只有 Lync 伺服器和 IMMCU 在作用中且可用。</span><span class="sxs-lookup"><span data-stu-id="324c9-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="324c9-117">「目前狀態」\*\* 可為使用者提供網路上其他使用者的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="324c9-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="324c9-118">使用者的目前狀態所提供的資訊有助於其他人決定是否應嘗試連絡該名使用者，以及是否要使用立即訊息、電話或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="324c9-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="324c9-119">目前狀態會促進立即通訊，但也會提供使用者正在開會中或不在辦公室的資訊，指出無法進行立即通訊。</span><span class="sxs-lookup"><span data-stu-id="324c9-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="324c9-120">此狀態會顯示為 Lync 及其他平台服務感知的應用程式，包括 Microsoft Outlook 傳訊與共同作業用戶端、 Microsoft SharePoint 技術、 Microsoft Word 和 Microsoft Excel 試算表中的目前狀態圖示軟體。</span><span class="sxs-lookup"><span data-stu-id="324c9-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="324c9-121">目前狀態圖示表示使用者目前是否有空，以及通訊意願。</span><span class="sxs-lookup"><span data-stu-id="324c9-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

