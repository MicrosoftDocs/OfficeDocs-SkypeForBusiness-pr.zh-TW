---
title: Lync Server 2013： 設定未指派號碼的宣告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 555c42a31d243ce53ff1eeb7713519771fef2f35
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="77279-102">在 Lync Server 2013 中設定未指派號碼的宣告</span><span class="sxs-lookup"><span data-stu-id="77279-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77279-103">_**主題上次修改日期：** 2012年-09-11_</span><span class="sxs-lookup"><span data-stu-id="77279-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="77279-104">宣告應用程式是企業語音功能，可讓您設定未指派的副檔名 （適用於您的組織，但不會指派給某個人或電話分機） 的呼叫會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="77279-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="77279-105">例如，您可以設定撥給未指派號碼的來電，以播放訊息或轉接至不同目的地，或兩者。</span><span class="sxs-lookup"><span data-stu-id="77279-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="77279-106">當您部署企業語音時，宣告應用程式被安裝為前端伺服器或 Standard Edition server 上的回應群組應用程式的功能。</span><span class="sxs-lookup"><span data-stu-id="77279-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="77279-107">您需要設定宣告，作法為上傳音訊檔案或設定文字轉換語音 (TTS)，以及設定未指派的號碼表。</span><span class="sxs-lookup"><span data-stu-id="77279-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="77279-108">本節會引導您完成的 Lync Server 宣告設定。</span><span class="sxs-lookup"><span data-stu-id="77279-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="77279-109">它會假設您已閱讀規劃章節相關的宣告，並部署 Enterprise Edition 伺服器或 Standard Edition 伺服器與 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="77279-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="77279-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="77279-110">In This Section</span></span>

  - [<span data-ttu-id="77279-111">宣告組態先決條件和 Lync Server 2013 中的角色</span><span class="sxs-lookup"><span data-stu-id="77279-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="77279-112">Lync Server 2013 中的宣告應用程式的部署程序</span><span class="sxs-lookup"><span data-stu-id="77279-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="77279-113">Lync Server 2013 中建立的宣告</span><span class="sxs-lookup"><span data-stu-id="77279-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="77279-114">在 Lync Server 2013 中設定未指派號碼表</span><span class="sxs-lookup"><span data-stu-id="77279-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="77279-115">（選用）確認 Lync Server 2013 中的宣告部署</span><span class="sxs-lookup"><span data-stu-id="77279-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77279-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="77279-116">See Also</span></span>


[<span data-ttu-id="77279-117">規劃 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="77279-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

