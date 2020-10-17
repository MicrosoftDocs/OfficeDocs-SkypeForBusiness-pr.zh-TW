---
title: Lync Server 2013：設定未指派號碼的宣告
description: Lync Server 2013：設定未指派號碼的宣告。
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
ms.openlocfilehash: 16ab636f0c6157118a00d5e46521555086c5e520
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570029"
---
# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="2c7de-103">在 Lync Server 2013 中設定未指派號碼的宣告</span><span class="sxs-lookup"><span data-stu-id="2c7de-103">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c7de-104">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="2c7de-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="2c7de-105">宣告應用程式是一種企業語音功能，可讓您設定呼叫未指派的分機號碼 (對組織有效的分機，但未指派給人員或電話) 。</span><span class="sxs-lookup"><span data-stu-id="2c7de-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="2c7de-106">例如，您可以設定撥給未指派號碼的來電，以播放訊息或轉接至不同目的地，或兩者。</span><span class="sxs-lookup"><span data-stu-id="2c7de-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="2c7de-107">當您部署企業語音時，會將宣告應用程式安裝為前端伺服器或 Standard Edition Server 上的回應群組應用程式功能。</span><span class="sxs-lookup"><span data-stu-id="2c7de-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="2c7de-108">您需要設定宣告，作法為上傳音訊檔案或設定文字轉換語音 (TTS)，以及設定未指派的號碼表。</span><span class="sxs-lookup"><span data-stu-id="2c7de-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="2c7de-109">本節會引導您完成 Lync Server 宣告的設定。</span><span class="sxs-lookup"><span data-stu-id="2c7de-109">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="2c7de-110">本範例假設您已閱讀與宣告相關的規劃區段，並已部署 Enterprise Edition server 或 Standard Edition server 與 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="2c7de-110">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2c7de-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="2c7de-111">In This Section</span></span>

  - [<span data-ttu-id="2c7de-112">Lync Server 2013 中的宣告設定必要條件和角色</span><span class="sxs-lookup"><span data-stu-id="2c7de-112">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="2c7de-113">Lync Server 2013 中宣告應用程式的部署程式</span><span class="sxs-lookup"><span data-stu-id="2c7de-113">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="2c7de-114">在 Lync Server 2013 中建立宣告</span><span class="sxs-lookup"><span data-stu-id="2c7de-114">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="2c7de-115">在 Lync Server 2013 中設定未指派號碼表</span><span class="sxs-lookup"><span data-stu-id="2c7de-115">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="2c7de-116"> 在 Lync Server 2013 中 (選用) 驗證宣告部署</span><span class="sxs-lookup"><span data-stu-id="2c7de-116">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2c7de-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2c7de-117">See Also</span></span>


[<span data-ttu-id="2c7de-118">在 Lync Server 2013 中規劃通話管理功能</span><span class="sxs-lookup"><span data-stu-id="2c7de-118">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

