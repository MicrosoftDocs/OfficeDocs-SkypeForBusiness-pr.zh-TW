---
title: Lync Server 2013：宣告應用程式的部署程式
description: Lync Server 2013：宣告應用程式的部署程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559977c32f63fae312164b5b0c36698fa13afb09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550989"
---
# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="61df1-103">Lync Server 2013 中宣告應用程式的部署程式</span><span class="sxs-lookup"><span data-stu-id="61df1-103">Deployment process for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61df1-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="61df1-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="61df1-105">本節概述部署宣告應用程式所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="61df1-105">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="61df1-106">您必須先部署 Enterprise Voice，才能設定宣告。</span><span class="sxs-lookup"><span data-stu-id="61df1-106">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="61df1-107">當您部署企業語音時，會安裝並啟用宣告應用程式所需的元件。</span><span class="sxs-lookup"><span data-stu-id="61df1-107">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="61df1-108">宣告部署程序</span><span class="sxs-lookup"><span data-stu-id="61df1-108">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61df1-109">階段</span><span class="sxs-lookup"><span data-stu-id="61df1-109">Phase</span></span></th>
<th><span data-ttu-id="61df1-110">步驟</span><span class="sxs-lookup"><span data-stu-id="61df1-110">Steps</span></span></th>
<th><span data-ttu-id="61df1-111">角色</span><span class="sxs-lookup"><span data-stu-id="61df1-111">Roles</span></span></th>
<th><span data-ttu-id="61df1-112">部署文件</span><span class="sxs-lookup"><span data-stu-id="61df1-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61df1-113">設定宣告設定</span><span class="sxs-lookup"><span data-stu-id="61df1-113">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="61df1-114">錄製及上傳音訊檔案，或是使用文字轉語音 (TTS)，以建立宣告。</span><span class="sxs-lookup"><span data-stu-id="61df1-114">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="61df1-115">設定未指派號碼表格中的未指派號碼範圍，並建立它們與適當宣告的關聯。</span><span class="sxs-lookup"><span data-stu-id="61df1-115">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="61df1-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="61df1-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="61df1-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="61df1-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="61df1-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="61df1-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="61df1-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="61df1-119">CsAdministrator</span></span></p>
<p><span data-ttu-id="61df1-120">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="61df1-120">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="61df1-121"><a href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中建立宣告</a></span><span class="sxs-lookup"><span data-stu-id="61df1-121"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="61df1-122"><a href="lync-server-2013-configure-the-unassigned-number-table.md">在 Lync Server 2013 中設定未指派號碼表</a></span><span class="sxs-lookup"><span data-stu-id="61df1-122"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61df1-123">驗證宣告部署</span><span class="sxs-lookup"><span data-stu-id="61df1-123">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="61df1-124">透過接聽宣告以驗證設定如預期運作。</span><span class="sxs-lookup"><span data-stu-id="61df1-124">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="61df1-125"><a href="lync-server-2013-optional-verify-announcement-deployment.md"> 在 Lync Server 2013 中 (選用) 驗證宣告部署</a></span><span class="sxs-lookup"><span data-stu-id="61df1-125"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

