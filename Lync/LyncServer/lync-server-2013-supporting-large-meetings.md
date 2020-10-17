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
ms.openlocfilehash: 19359dd785b846fa765e72adb810ccd255c2bd2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523920"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="74962-102">使用 Lync Server 2013 支援大型會議</span><span class="sxs-lookup"><span data-stu-id="74962-102">Supporting large meetings using Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74962-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="74962-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="74962-104">大型會議因為具有下列特性，所以不適用上一節中所述的測試模型：</span><span class="sxs-lookup"><span data-stu-id="74962-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="74962-105">會議格式是一對多簡報。</span><span class="sxs-lookup"><span data-stu-id="74962-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="74962-106">只有一位或少數使用者是簡報者，其他人都是以出席者的身分參加會議。</span><span class="sxs-lookup"><span data-stu-id="74962-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="74962-107">PowerPoint 簡報共用是主要的資料共同作業活動。</span><span class="sxs-lookup"><span data-stu-id="74962-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="74962-108">音訊是必要的，也可以使用視訊。</span><span class="sxs-lookup"><span data-stu-id="74962-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="74962-109">代理通常是由會囈召集人或召集人的助理擔任，要在會前做好準備工作。</span><span class="sxs-lookup"><span data-stu-id="74962-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="74962-110">代理 (非簡報者) 負責會議進行，包括與線上會議連線、確認音訊、視訊和投影片共用的運作、管理大廳與使用者角色、設定或取消設定參與者的靜音功能、記錄問題以及管理錄音。</span><span class="sxs-lookup"><span data-stu-id="74962-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="74962-111">支援最多 1000 位使用者的大型會議需要同時解決共用硬體模型和非保留模型的相關問題。</span><span class="sxs-lookup"><span data-stu-id="74962-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="74962-112">為了讓最多1000使用者的會議具有足夠的 CPU 和記憶體資源，主控前端伺服器不應主控任何其他立即訊息 (IM) 和目前狀態或企業語音工作負載。</span><span class="sxs-lookup"><span data-stu-id="74962-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="74962-113">不論其他的會議大小為何，它也不會主控任何其他會議。</span><span class="sxs-lookup"><span data-stu-id="74962-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="74962-114">這表示將最多1000使用者的主控會議，需要設定個別的 Lync 伺服器集區，專門主控最多1000使用者的大型會議。</span><span class="sxs-lookup"><span data-stu-id="74962-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="74962-115">專用於主控大型會議的 Lync 伺服器集區，一次只能裝載一或1000多個會議，所以必須透過帶外排程過程預先保留會議時間，以確保前端伺服器的專屬支援。</span><span class="sxs-lookup"><span data-stu-id="74962-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="74962-116">如果要同時支援多場大型會議，建議您設定多個專屬的大型會議集區。</span><span class="sxs-lookup"><span data-stu-id="74962-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="74962-p103">我們建議請一位代理來進行及監控大型會議的線上部分。這位代理可能是召集人、召集人或簡報者的代理人或是專屬的大型會議支援團隊的成員，視組織的喜好而定。</span><span class="sxs-lookup"><span data-stu-id="74962-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="74962-119">在下列各節中，我們將說明如何針對大型會議實施專屬集區，包括使用 Lync Server 2013 以支援大型會議案例的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="74962-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="74962-120">本章節內容</span><span class="sxs-lookup"><span data-stu-id="74962-120">In This Section</span></span>

  - [<span data-ttu-id="74962-121">在 Lync Server 2013 中設定大型會議的支援</span><span class="sxs-lookup"><span data-stu-id="74962-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="74962-122">在 Lync Server 2013 中管理大型會議</span><span class="sxs-lookup"><span data-stu-id="74962-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

