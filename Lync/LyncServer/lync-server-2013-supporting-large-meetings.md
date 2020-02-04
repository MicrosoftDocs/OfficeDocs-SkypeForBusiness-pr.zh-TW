---
title: Lync Server 2013：支援大型會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d2c36d99bc5af62771aabb643df1223db3a291c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="fbb36-102">使用 Lync Server 2013 支援大型會議</span><span class="sxs-lookup"><span data-stu-id="fbb36-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbb36-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fbb36-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fbb36-104">大型會議不遵循上一節所述的測試模型，因為它們具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="fbb36-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="fbb36-105">會議格式是一對多份簡報。</span><span class="sxs-lookup"><span data-stu-id="fbb36-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="fbb36-106">一或幾個使用者是簡報者，而其他人則只參與為出席者。</span><span class="sxs-lookup"><span data-stu-id="fbb36-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="fbb36-107">PowerPoint 簡報共用是主要的資料共同作業活動。</span><span class="sxs-lookup"><span data-stu-id="fbb36-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="fbb36-108">音訊是必要的，也可能會使用影片。</span><span class="sxs-lookup"><span data-stu-id="fbb36-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="fbb36-109">專屬人員，通常是會議召集人或召集人的助手會提前設定會議。</span><span class="sxs-lookup"><span data-stu-id="fbb36-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="fbb36-110">專用員工（而不是簡報者）會執行會議，包括連線至線上會議、驗證音訊、影片及投影片共用工作、管理大廳及使用者角色、靜音及 unmuting 參與者、提出問題，以及管理錄製（例如適宜.</span><span class="sxs-lookup"><span data-stu-id="fbb36-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="fbb36-111">支援最多1000使用者的大型會議，需要解決與共享硬體模型和無保留模型相關的問題。</span><span class="sxs-lookup"><span data-stu-id="fbb36-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="fbb36-112">若要在最多1000使用者的會議中擁有充足的 CPU 和記憶體資源，託管前端伺服器不應該託管任何其他的立即訊息（IM）與目前狀態或企業語音工作負載。</span><span class="sxs-lookup"><span data-stu-id="fbb36-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="fbb36-113">不論其他會議的規模為何，它也不會主持任何其他會議。</span><span class="sxs-lookup"><span data-stu-id="fbb36-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="fbb36-114">這代表將最多1000個使用者的主機託管會議，需要設定一個專用的 Lync 伺服器池，專門用來託管大型會議，最多1000個使用者。</span><span class="sxs-lookup"><span data-stu-id="fbb36-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="fbb36-115">專用來主持大型會議的 Lync Server pool 應該同時主持一或多達1000的使用者，因此必須透過不限頻帶的排程程式來預先預留會議時間，以確保從前端 Serv 的專屬支援ers.</span><span class="sxs-lookup"><span data-stu-id="fbb36-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="fbb36-116">若要同時支援多個大型會議，建議您設定多個專用大型會議池。</span><span class="sxs-lookup"><span data-stu-id="fbb36-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="fbb36-117">我們建議將一個專門的人員執行並監視大型會議的線上部分。</span><span class="sxs-lookup"><span data-stu-id="fbb36-117">We recommend that a dedicated person run and monitor the online portion of a large meeting.</span></span> <span data-ttu-id="fbb36-118">根據組織的喜好設定，此人可能是召集人、召集人或簡報者的代理人，或是專屬大型會議支援小組的成員。</span><span class="sxs-lookup"><span data-stu-id="fbb36-118">This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="fbb36-119">在下列各節中，我們將說明如何針對大型會議實施專用的 pool，包括使用 Lync Server 2013 支援大型會議案例的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="fbb36-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fbb36-120">本節內容</span><span class="sxs-lookup"><span data-stu-id="fbb36-120">In This Section</span></span>

  - [<span data-ttu-id="fbb36-121">在 Lync Server 2013 中設定大型會議的支援</span><span class="sxs-lookup"><span data-stu-id="fbb36-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="fbb36-122">在 Lync Server 2013 中管理大型會議</span><span class="sxs-lookup"><span data-stu-id="fbb36-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

