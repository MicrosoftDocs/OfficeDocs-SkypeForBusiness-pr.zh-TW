---
title: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的特性與功能
description: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的功能。
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
ms.openlocfilehash: b5c8bc3db255228da3366eb5aa142cd5adc233d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543409"
---
# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="29816-103">Lync Server 2013 中前端伺服器、立即訊息及顯示狀態的功能</span><span class="sxs-lookup"><span data-stu-id="29816-103">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29816-104">_**主題上次修改日期：** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="29816-104">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="29816-105">前端伺服器提供大部分的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="29816-105">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="29816-106">有兩種可供使用的版本： Lync Server Enterprise Edition 主要專為較大的組織和 Lync Server Standard Edition 設計，其主要是針對需要較小硬體 investement 且不需要高可用性的小型組織所設計。</span><span class="sxs-lookup"><span data-stu-id="29816-106">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="29816-107">這兩種版本都支援所有的 Lync Server 工作負載，包括 IM、顯示狀態、會議及 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="29816-107">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="29816-p102">立即訊息 (IM) 可讓使用者在電腦上使用文字訊息，與其他使用者進行即時溝通。同時支援雙方或多方 IM 工作階段。雙方 IM 交談中的參與者可以隨時將第三個參與者加入交談中。若發生這種情況，[交談] 視窗會變更成可支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="29816-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="29816-112">Lync 和 Communicator 用戶端與單一通訊相關時，通常稱為對等。</span><span class="sxs-lookup"><span data-stu-id="29816-112">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="29816-113">從技術角度來看，這兩個用戶端是透過單一交談進行通訊，而立即訊息 multipoint control unit (IMMCU) 中間。</span><span class="sxs-lookup"><span data-stu-id="29816-113">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="29816-114">IMMCU 是前端伺服器的元件。</span><span class="sxs-lookup"><span data-stu-id="29816-114">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="29816-115">在所需的通訊工作流程中放置 IMMCU，可讓您在前端伺服器上啟用詳細通話記錄及其他功能。</span><span class="sxs-lookup"><span data-stu-id="29816-115">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="29816-116">通訊來自用戶端的動態來源埠至前端伺服器埠 TLS/TCP/5061 (假設使用建議的傳輸層安全性) 。</span><span class="sxs-lookup"><span data-stu-id="29816-116">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="29816-117">根據設計，對等通訊 (，而且只有在 Lync Server 和 IMMCU 為使用中且可用時，才可以進行多方的 IM) 。</span><span class="sxs-lookup"><span data-stu-id="29816-117">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="29816-118">「目前狀態」\*\* 可為使用者提供網路上其他使用者的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="29816-118">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="29816-119">使用者的目前狀態所提供的資訊有助於其他人決定是否應嘗試連絡該名使用者，以及是否要使用立即訊息、電話或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="29816-119">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="29816-120">目前狀態會促進立即通訊，但也會提供使用者正在開會中或不在辦公室的資訊，指出無法進行立即通訊。</span><span class="sxs-lookup"><span data-stu-id="29816-120">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="29816-121">這種目前狀態會顯示為 Lync 中的目前狀態圖示及其他狀態識別應用程式，包括 Microsoft Outlook 訊息和共同作業用戶端、Microsoft SharePoint 技術、Microsoft Word 和 Microsoft Excel 試算表軟體。</span><span class="sxs-lookup"><span data-stu-id="29816-121">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="29816-122">目前狀態圖示表示使用者目前是否有空，以及通訊意願。</span><span class="sxs-lookup"><span data-stu-id="29816-122">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

