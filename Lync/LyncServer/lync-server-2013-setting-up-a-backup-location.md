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
ms.openlocfilehash: 723bcbc2aeaae5264645d824a9b10a939b6770ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="6c076-102">設定 Lync Server 2013 的備份位置</span><span class="sxs-lookup"><span data-stu-id="6c076-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c076-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="6c076-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="6c076-104">在您第一次備份 Lync Server 前，請先設定要儲存及維護備份所需的硬體和軟體。</span><span class="sxs-lookup"><span data-stu-id="6c076-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="6c076-105">您必須視需要取得媒體和內容的存取權，並提供要備份的每個伺服器與備份媒體之間的網路連線。</span><span class="sxs-lookup"><span data-stu-id="6c076-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="6c076-106">您所使用的媒體和位置應該在您的備份和還原策略中定義。</span><span class="sxs-lookup"><span data-stu-id="6c076-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="6c076-107">您在一般備份中使用的位置可以是本機或遠端，但必須是安全的，而且在備份和還原時必須是可存取的。</span><span class="sxs-lookup"><span data-stu-id="6c076-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="6c076-108">我們建議您使用遠端位置來防範主要網站上的災難性事件。</span><span class="sxs-lookup"><span data-stu-id="6c076-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="6c076-109">在您設定並測試個別元件之後，請確認每個伺服器上的備份的協助工具。</span><span class="sxs-lookup"><span data-stu-id="6c076-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

