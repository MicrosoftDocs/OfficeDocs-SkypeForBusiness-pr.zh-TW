---
title: Lync Server 2013：設定備份位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ee86d2cf3d68b65c03e851980b21fb0293c5362
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509740"
---
# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="e181a-102">設定 Lync Server 2013 的備份位置</span><span class="sxs-lookup"><span data-stu-id="e181a-102">Setting up a backup location for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e181a-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="e181a-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="e181a-104">在您第一次備份 Lync Server 之前，請先設定所需的硬體和軟體，以便儲存及維護備份。</span><span class="sxs-lookup"><span data-stu-id="e181a-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="e181a-105">您必須視情況取得媒體和內容的存取權，並提供每部要備份伺服器與備份媒體之間的網路連線。</span><span class="sxs-lookup"><span data-stu-id="e181a-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="e181a-106">您應在備份和還原策略中定義您使用的媒體和位置。</span><span class="sxs-lookup"><span data-stu-id="e181a-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="e181a-107">您用於定期備份的位置可以是本機或遠端的，但必須是安全的，而且必須可存取備份與還原。</span><span class="sxs-lookup"><span data-stu-id="e181a-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="e181a-108">我們建議使用遠端位置，以防範主要網站上的災難性事件。</span><span class="sxs-lookup"><span data-stu-id="e181a-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="e181a-109">當您設定好並測試過個別元件後，請從每部伺服器驗證備份的可存取性。</span><span class="sxs-lookup"><span data-stu-id="e181a-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

