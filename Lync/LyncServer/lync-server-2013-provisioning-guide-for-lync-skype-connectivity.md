---
title: Lync Server 2013：提供 Lync-Skype 連線的指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 073d7c583c6d159e1b262421e441a56c9d081928
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513160"
---
# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="f7795-102">Lync Server 2013 中的 Lync-Skype 連線布配指南</span><span class="sxs-lookup"><span data-stu-id="f7795-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7795-103">_**主題上次修改日期：** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="f7795-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="f7795-104">Lync Server 2013 支援與 Skype 的連線能力。</span><span class="sxs-lookup"><span data-stu-id="f7795-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="f7795-105">這種連線功能可讓您的 Lync 2013 使用者使用 Skype 使用者的 Microsoft 帳戶 (MSA) 新增 Skype 連絡人。</span><span class="sxs-lookup"><span data-stu-id="f7795-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="f7795-106">Skype 用戶端也可以將 Lync 使用者新增至其連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="f7795-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="f7795-107">根據在 Lync Server 中以管理方式設定的原則，Lync 和 Skype 使用者將能夠使用立即訊息進行通訊、查看彼此的狀態，以及啟動音訊和影片通話。</span><span class="sxs-lookup"><span data-stu-id="f7795-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="f7795-108">Lync-Skype 連線也是 Lync Online 的一項功能，可在 Microsoft 365 系統管理中心內的 Lync 系統管理中心啟用 Lync Online 客戶。</span><span class="sxs-lookup"><span data-stu-id="f7795-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="f7795-109">如果 Lync Server 已設定為使用公用立即訊息連線功能與 Windows Messenger 進行連線， (PIC) ，您的部署已設定為 Lync-Skype 連線性。</span><span class="sxs-lookup"><span data-stu-id="f7795-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="f7795-110">您可能想要考慮的唯一變更是將現有的 Messenger PIC 專案重新命名為 Skype。</span><span class="sxs-lookup"><span data-stu-id="f7795-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="f7795-111">如需詳細資訊，請參閱本指南稍後的設定 Lync 的 Skype PIC 提供者設定。</span><span class="sxs-lookup"><span data-stu-id="f7795-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f7795-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f7795-112">In This Section</span></span>

  - [<span data-ttu-id="f7795-113">有關 Lync Online 客戶在 Lync Server 2013 中 Lync-Skype 連線的附注</span><span class="sxs-lookup"><span data-stu-id="f7795-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="f7795-114">從 Lync Server 2013 存取 Lync Server 公用 IM 連線布建網站</span><span class="sxs-lookup"><span data-stu-id="f7795-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="f7795-115">在 Lync Server 2013 中啟用 Lync-Skype 連線能力</span><span class="sxs-lookup"><span data-stu-id="f7795-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="f7795-116">在 Lync Server 2013 中使用 Lync-Skype 連線能力做為使用者</span><span class="sxs-lookup"><span data-stu-id="f7795-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="f7795-117">常見問題：布建 Lync Server 2013 for Skype connectivity</span><span class="sxs-lookup"><span data-stu-id="f7795-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

