---
title: Lync Server 2013： 設定備份的位置
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
ms.openlocfilehash: e5b47a866b4ce1a731d282c78e09c1afb3c91af7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="2a2eb-102">設定 Lync Server 2013 的備份位置</span><span class="sxs-lookup"><span data-stu-id="2a2eb-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a2eb-103">_**上次修改主題：** 2013年-02-17_</span><span class="sxs-lookup"><span data-stu-id="2a2eb-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="2a2eb-104">您需要您的 Lync Server 的第一個備份之前，請設定硬體和軟體才能儲存及維護備份需要。</span><span class="sxs-lookup"><span data-stu-id="2a2eb-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="2a2eb-105">您必須視情況取得媒體和內容的存取權，並提供每部要備份伺服器與備份媒體之間的網路連線。</span><span class="sxs-lookup"><span data-stu-id="2a2eb-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="2a2eb-106">備份及還原策略中，應該要定義的媒體和您所使用的位置。</span><span class="sxs-lookup"><span data-stu-id="2a2eb-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="2a2eb-107">您用於定期備份的位置可以是本機或遠端，但必須是安全，且必須是可用於備份及還原。</span><span class="sxs-lookup"><span data-stu-id="2a2eb-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="2a2eb-108">我們建議您使用遠端位置，以防範災難性的事件，在您主要的網站。</span><span class="sxs-lookup"><span data-stu-id="2a2eb-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="2a2eb-109">當您設定好並測試過個別元件後，請從每部伺服器驗證備份的可存取性。</span><span class="sxs-lookup"><span data-stu-id="2a2eb-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

