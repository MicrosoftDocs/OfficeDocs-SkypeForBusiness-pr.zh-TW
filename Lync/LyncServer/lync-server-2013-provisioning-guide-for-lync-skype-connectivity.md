---
title: Lync Server 2013： 佈建 Lync Skype 連線的快速入門
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
ms.openlocfilehash: e8f6e1b9262e0e7ed0f9060f3e509924aee9ba62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="857d9-102">適用於 Lync Server 2013 中的 Lync Skype 連線佈建指南</span><span class="sxs-lookup"><span data-stu-id="857d9-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="857d9-103">_**上次修改主題：** 2014年-11-26_</span><span class="sxs-lookup"><span data-stu-id="857d9-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="857d9-104">Lync Server 2013 支援與 Skype 進行連線。</span><span class="sxs-lookup"><span data-stu-id="857d9-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="857d9-105">此連線可以讓您使用 Skype 使用者的 Microsoft 帳戶 (MSA) 新增 Skype 連絡人的 Lync 2013 使用者。</span><span class="sxs-lookup"><span data-stu-id="857d9-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="857d9-106">Skype 用戶端也可以將 Lync 使用者新增至其連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="857d9-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="857d9-107">根據行政規定必須在 Lync Server 中設定的原則、 Lync 與 Skype 使用者能夠使用立即訊息通訊，請參閱彼此的目前狀態及啟動音訊和視訊通話。</span><span class="sxs-lookup"><span data-stu-id="857d9-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="857d9-108">Lync Skype 連線也是 Lync Online 的功能，並可啟用從 Office 365 入口網站內 Lync 系統管理中心的 Lync Online 客戶。</span><span class="sxs-lookup"><span data-stu-id="857d9-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="857d9-109">Lync Server 已設為使用公用立即訊息連線 (PIC) 連線與 Windows Messenger，如果您的部署已設定 Lync Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="857d9-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="857d9-110">您可能要考慮的唯一變更是重新命名為 Skype 您現有 Messenger PIC 項目。</span><span class="sxs-lookup"><span data-stu-id="857d9-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="857d9-111">如需詳細資訊，請參閱本指南稍後設定 lync Skype PIC 提供者設定。</span><span class="sxs-lookup"><span data-stu-id="857d9-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="857d9-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="857d9-112">In This Section</span></span>

  - [<span data-ttu-id="857d9-113">附註在 Lync Server 2013 中的 Lync Skype 連線的相關的 Lync Online 客戶</span><span class="sxs-lookup"><span data-stu-id="857d9-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="857d9-114">存取佈建網站從 Lync Server 2013 的 Lync Server 公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="857d9-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="857d9-115">啟用 Lync Server 2013 中的 Lync Skype 連線能力</span><span class="sxs-lookup"><span data-stu-id="857d9-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="857d9-116">使用 Lync Server 2013 中的 Lync Skype 連線，以使用者身分</span><span class="sxs-lookup"><span data-stu-id="857d9-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="857d9-117">常見問題： 佈建 Lync Server 2013 的 Skype 連線</span><span class="sxs-lookup"><span data-stu-id="857d9-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

