---
title: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739825eed3c8a3ba8239849e0c17c449180a2d95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="20429-102">Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的功能</span><span class="sxs-lookup"><span data-stu-id="20429-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20429-103">_**主題上次修改日期：** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="20429-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="20429-104">前端伺服器提供大部分的 Lync 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="20429-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="20429-105">有兩個可用的版本： Lync Server Enterprise Edition，主要針對大型組織和 Lync Server Standard Edition 設計，主要針對需要較小硬體 investement 且不需要的較小組織。需要高可用性。</span><span class="sxs-lookup"><span data-stu-id="20429-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="20429-106">這兩種版本都支援所有 Lync 伺服器的工作負載，包括 IM、目前狀態、會議和企業語音。</span><span class="sxs-lookup"><span data-stu-id="20429-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="20429-107">[立即訊息（IM）] 可讓您的使用者在電腦上使用文字型郵件即時相互通訊。</span><span class="sxs-lookup"><span data-stu-id="20429-107">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="20429-108">支援兩方和多方 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="20429-108">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="20429-109">在雙方的 IM 交談中，參與者可以隨時新增協力廠商參與者加入交談。</span><span class="sxs-lookup"><span data-stu-id="20429-109">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="20429-110">發生這種情況時，交談視窗會變更以支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="20429-110">When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="20429-111">當 Lync 與 Communicator 用戶端參與單一通訊時，通常稱為對等。</span><span class="sxs-lookup"><span data-stu-id="20429-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="20429-112">從技術角度來看，兩個用戶端都是以單一交談的方式進行通訊，中間是中間的立即訊息 multipoint 控制項單位（IMMCU）。</span><span class="sxs-lookup"><span data-stu-id="20429-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="20429-113">IMMCU 是前端伺服器的元件。</span><span class="sxs-lookup"><span data-stu-id="20429-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="20429-114">將 IMMCU 放在所需的通訊工作流程中，即可允許通話詳細資料錄製，以及前端伺服器所能啟用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="20429-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="20429-115">通訊來自用戶端上的動態來源埠到前端伺服器埠 TLS/TCP/5061 （假設使用建議的傳輸層安全性）。</span><span class="sxs-lookup"><span data-stu-id="20429-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="20429-116">透過設計、對等通訊（以及多方 IM），只有當 Lync Server 與 IMMCU 處於作用中且可用時，才可以使用。</span><span class="sxs-lookup"><span data-stu-id="20429-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="20429-117">[*目前狀態] 提供資訊*給使用者，瞭解網路上其他人的狀態。</span><span class="sxs-lookup"><span data-stu-id="20429-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="20429-118">使用者的目前狀態會提供資訊，協助其他人決定是否應該嘗試與使用者聯繫，以及是否要使用立即訊息、電話或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="20429-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="20429-119">如果可能的話，目前狀態會鼓勵立即通訊，但它也會提供使用者是否在會議中或不在辦公室的相關資訊，指出無法進行立即通訊。</span><span class="sxs-lookup"><span data-stu-id="20429-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="20429-120">在 Lync 和其他存在感知的應用程式中，此目前狀態會顯示為「目前狀態」圖示，包括 Microsoft Outlook 訊息與共同作業用戶端、Microsoft SharePoint 技術、Microsoft Word 及 Microsoft Excel 試算表軟體.</span><span class="sxs-lookup"><span data-stu-id="20429-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="20429-121">[目前狀態] 圖示代表使用者目前的可用性和溝通意願。</span><span class="sxs-lookup"><span data-stu-id="20429-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

