---
title: Lync Server 2013：Lync Server 2013 的 Lync-Skype 連線佈建指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f595916502a7c7ec27ff220a7b3f138b41e6fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="c271f-102">Lync Server 2013 的 Lync-Skype 連線佈建指南</span><span class="sxs-lookup"><span data-stu-id="c271f-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c271f-103">_**主題上次修改日期：** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="c271f-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="c271f-p101">Lync Server 2013 支援與 Skype 的連線。此連線功能可讓 Lync 2013 使用者利用 Skype 使用者的 Microsoft 帳戶 (MSA) 新增 Skype 連絡人。Skype 用戶端亦可將 Lync 使用者新增至其連絡人清單。根據在 Lync Server 中所設定的系統管理原則，Lync 與 Skype 使用者將可使用立即訊息進行通訊、查看彼此的目前狀態，以及啟動音訊和視訊通話。Lync-Skype 連線同時也是 Lync Online 的一項功能，可透過 Office 365 入口網站中的 Lync 系統管理中心為 Lync Online 客戶進行啟用。</span><span class="sxs-lookup"><span data-stu-id="c271f-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="c271f-p102">如果 Lync Server 已設定為透過公用立即訊息連線 (PIC) 來與 Windows Messenger 連線，則表示您的部署已完成設定，可進行 Lync-Skype 連線。唯一需要考慮進行的變更就是將現有的 Messenger PIC 項目重新命名為 Skype。如需詳細資料，請參閱本指南後文中的＜針對 Lync 設定 Skype PIC 提供者設定＞。</span><span class="sxs-lookup"><span data-stu-id="c271f-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c271f-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="c271f-112">In This Section</span></span>

  - [<span data-ttu-id="c271f-113">有關 lync Online 客戶的 lync Server 2013 中的 Lync-Skype 連線性注意事項</span><span class="sxs-lookup"><span data-stu-id="c271f-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="c271f-114">透過 Lync Server 2013 存取 Lync Server 公用 IM 連線佈建網站</span><span class="sxs-lookup"><span data-stu-id="c271f-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="c271f-115">在 Lync Server 2013 中啟用 Lync-Skype 連線功能</span><span class="sxs-lookup"><span data-stu-id="c271f-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="c271f-116">在 Lync Server 2013 中以使用者身分使用 Lync-Skype 連線</span><span class="sxs-lookup"><span data-stu-id="c271f-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="c271f-117">常見問題集：佈建 Lync Server 以供 Skype 連線</span><span class="sxs-lookup"><span data-stu-id="c271f-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

