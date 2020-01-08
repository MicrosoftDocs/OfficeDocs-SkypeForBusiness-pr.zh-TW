---
title: Lync Server 2013：大型會議支援常見問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="a6946-102">大型會議支援 Lync Server 2013 的常見問題</span><span class="sxs-lookup"><span data-stu-id="a6946-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6946-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="a6946-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="a6946-104">下列各節提供建立及執行大型會議的常見問題的解答。</span><span class="sxs-lookup"><span data-stu-id="a6946-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="a6946-105">問：有多少使用者可以參與大型會議？</span><span class="sxs-lookup"><span data-stu-id="a6946-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="a6946-106">Lync Server 使用者模型會指定共用區中的250使用者限制，或是在專用於大型會議的池中的1000使用者，但這些數位只代表我們已測試的使用者數量，而且只代表我們在測試中使用的特定硬體組。</span><span class="sxs-lookup"><span data-stu-id="a6946-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="a6946-107">根據我們的測試，我們建議對最大大小的限制。</span><span class="sxs-lookup"><span data-stu-id="a6946-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="a6946-108">不過，您可以設定一或多個會議原則（您是使用 Lync Server 管理命令介面中的 Windows PowerShell Cmdlet 設定，或是使用 Lync Server），來控制貴組織中的會議所允許的實際參與者人數[控制台]）。</span><span class="sxs-lookup"><span data-stu-id="a6946-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="a6946-109">您在會議原則中指定的數位可以是介於1和4294967295之間的任何32位整數，但建議的大小介於2與250參與者之間（含）。預設值為250。</span><span class="sxs-lookup"><span data-stu-id="a6946-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="a6946-110">問：我可以在擁有大量會議的池中擁有多少個會議或其他工作負載？</span><span class="sxs-lookup"><span data-stu-id="a6946-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="a6946-111">為了確保最多1000參與者的大型會議中的最佳使用者體驗，我們建議您只在專門針對大型會議的池中，一次只託管一個大型會議。</span><span class="sxs-lookup"><span data-stu-id="a6946-111">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings.</span></span> <span data-ttu-id="a6946-112">我們也建議您在大型會議進行期間，不允許任何其他工作負荷在該池中執行。</span><span class="sxs-lookup"><span data-stu-id="a6946-112">We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="a6946-113">問：是否應該將大型會議的召集人託管在專用的池中？</span><span class="sxs-lookup"><span data-stu-id="a6946-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="a6946-114">不。</span><span class="sxs-lookup"><span data-stu-id="a6946-114">No.</span></span> <span data-ttu-id="a6946-115">我們建議您不要將專用員工以外的任何使用者集中管理，以在專用的泳池上管理大型會議。</span><span class="sxs-lookup"><span data-stu-id="a6946-115">We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool.</span></span> <span data-ttu-id="a6946-116">這可防止其他即時通訊流量造成在該池中託管大型會議的問題。</span><span class="sxs-lookup"><span data-stu-id="a6946-116">This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool.</span></span> <span data-ttu-id="a6946-117">您應該使用大型會議排程員工的使用者帳戶，在專用的泳池上排程大型會議。</span><span class="sxs-lookup"><span data-stu-id="a6946-117">You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff.</span></span> <span data-ttu-id="a6946-118">您應該將會議召集人的使用者帳戶（要求大型會議的使用者）新增為大型會議的簡報者。</span><span class="sxs-lookup"><span data-stu-id="a6946-118">You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="a6946-119">問：我可以在大型會議中使用哪些媒體形式？</span><span class="sxs-lookup"><span data-stu-id="a6946-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="a6946-120">最多1000個使用者可包含音訊、影片、PowerPoint 共用、白板和目前狀態輪詢等大型會議。</span><span class="sxs-lookup"><span data-stu-id="a6946-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="a6946-121">問：我可以在大型會議中使用群組立即訊息（IM）嗎？</span><span class="sxs-lookup"><span data-stu-id="a6946-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="a6946-122">是。</span><span class="sxs-lookup"><span data-stu-id="a6946-122">Yes.</span></span> <span data-ttu-id="a6946-123">不過，大量的立即訊息（尤其是當由大量會議參與者傳送時），會因為 IM 視窗中的快速文字滾動問題而影響使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="a6946-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="a6946-124">傳送大量立即訊息給1000的使用者也可能會造成大量的伺服器負載，這可能會影響效能。</span><span class="sxs-lookup"><span data-stu-id="a6946-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="a6946-125">一般來說，只有問題與解答（Q\&As）才需要 IM。</span><span class="sxs-lookup"><span data-stu-id="a6946-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="a6946-126">使用者可以從手機撥入來加入大型會議嗎？</span><span class="sxs-lookup"><span data-stu-id="a6946-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="a6946-127">是。</span><span class="sxs-lookup"><span data-stu-id="a6946-127">Yes.</span></span> <span data-ttu-id="a6946-128">如果 Lync Server 2013 池已正確部署且已啟用電話撥入式會議，使用者將能夠撥入來加入大型會議。</span><span class="sxs-lookup"><span data-stu-id="a6946-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="a6946-129">我們的測試顯示，最多15% 的1000使用者可以在10分鐘內加入大型會議。</span><span class="sxs-lookup"><span data-stu-id="a6946-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="a6946-130">問：我可以在虛擬拓朴中主持大型會議嗎？</span><span class="sxs-lookup"><span data-stu-id="a6946-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="a6946-131">我們未在虛擬拓撲中測試大型會議，因此我們不支援使用虛擬機器來託管大型會議的專用池。</span><span class="sxs-lookup"><span data-stu-id="a6946-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

