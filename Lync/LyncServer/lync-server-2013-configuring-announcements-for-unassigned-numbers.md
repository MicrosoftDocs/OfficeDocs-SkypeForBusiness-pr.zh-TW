---
title: Lync Server 2013：設定未指派號碼的宣告
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
ms.openlocfilehash: 52d7e8ad1aa4fcfe3db9aabee61e317810707194
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="47e78-102">在 Lync Server 2013 中設定未指派號碼的宣告</span><span class="sxs-lookup"><span data-stu-id="47e78-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47e78-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="47e78-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="47e78-104">[宣告] 應用程式是一種企業語音功能，可讓您設定呼叫未指派的延伸（對貴組織有效，但未指派給人員或電話的延伸）。</span><span class="sxs-lookup"><span data-stu-id="47e78-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="47e78-105">例如，您可以設定未指派號碼的呼叫來播放郵件，或將其傳送至不同的目的地，或兩者皆可。</span><span class="sxs-lookup"><span data-stu-id="47e78-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="47e78-106">發佈應用程式是在您部署企業語音時，在前端伺服器或標準版伺服器上作為回應群組應用程式的功能安裝。</span><span class="sxs-lookup"><span data-stu-id="47e78-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="47e78-107">您必須先上傳音訊檔案或設定文字轉換語音（TTS）及設定 [未指定的數位] 資料表來設定宣告。</span><span class="sxs-lookup"><span data-stu-id="47e78-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="47e78-108">本節將引導您完成 Lync Server 宣告的設定。</span><span class="sxs-lookup"><span data-stu-id="47e78-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="47e78-109">它假設您已閱讀與宣告相關的規劃區段，以及使用企業語音部署企業版伺服器或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="47e78-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47e78-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="47e78-110">In This Section</span></span>

  - [<span data-ttu-id="47e78-111">Lync Server 2013 中的宣告組態先決條件和角色</span><span class="sxs-lookup"><span data-stu-id="47e78-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="47e78-112">Lync Server 2013 中宣告應用程式的部署程式</span><span class="sxs-lookup"><span data-stu-id="47e78-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="47e78-113">在 Lync Server 2013 中建立公告</span><span class="sxs-lookup"><span data-stu-id="47e78-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="47e78-114">在 Lync Server 2013 中設定未指派號碼表</span><span class="sxs-lookup"><span data-stu-id="47e78-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="47e78-115">可選驗證 Lync Server 2013 中的宣告部署</span><span class="sxs-lookup"><span data-stu-id="47e78-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47e78-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="47e78-116">See Also</span></span>


[<span data-ttu-id="47e78-117">規劃 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="47e78-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

