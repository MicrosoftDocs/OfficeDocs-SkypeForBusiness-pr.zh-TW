---
title: Lync Server 2013：宣告應用程式的部署程式
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
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="65282-102">Lync Server 2013 中宣告應用程式的部署程式</span><span class="sxs-lookup"><span data-stu-id="65282-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65282-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="65282-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="65282-104">本節概要說明部署宣告應用程式所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="65282-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="65282-105">您必須先部署企業語音，然後才能設定宣告。</span><span class="sxs-lookup"><span data-stu-id="65282-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="65282-106">當您部署企業語音時，會安裝並啟用宣告應用程式所需的元件。</span><span class="sxs-lookup"><span data-stu-id="65282-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="65282-107">發佈部署程式</span><span class="sxs-lookup"><span data-stu-id="65282-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65282-108">分</span><span class="sxs-lookup"><span data-stu-id="65282-108">Phase</span></span></th>
<th><span data-ttu-id="65282-109">步驟</span><span class="sxs-lookup"><span data-stu-id="65282-109">Steps</span></span></th>
<th><span data-ttu-id="65282-110">角色</span><span class="sxs-lookup"><span data-stu-id="65282-110">Roles</span></span></th>
<th><span data-ttu-id="65282-111">部署檔</span><span class="sxs-lookup"><span data-stu-id="65282-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65282-112">設定宣告設定</span><span class="sxs-lookup"><span data-stu-id="65282-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="65282-113">透過錄製及上傳音訊檔案或使用文字轉換語音（TTS）來建立公告。</span><span class="sxs-lookup"><span data-stu-id="65282-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="65282-114">在 [未指定的數位] 資料表中設定未指定的數位範圍，並將它們與適當的宣告建立關聯。</span><span class="sxs-lookup"><span data-stu-id="65282-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="65282-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="65282-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="65282-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="65282-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="65282-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="65282-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="65282-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="65282-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="65282-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="65282-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="65282-120"><a href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中建立公告</a></span><span class="sxs-lookup"><span data-stu-id="65282-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="65282-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">在 Lync Server 2013 中設定未指派號碼表</a></span><span class="sxs-lookup"><span data-stu-id="65282-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65282-122">確認您的宣告部署</span><span class="sxs-lookup"><span data-stu-id="65282-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="65282-123">透過聆聽宣告來測試，以確認您的設定如預期的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="65282-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="65282-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">可選驗證 Lync Server 2013 中的宣告部署</a></span><span class="sxs-lookup"><span data-stu-id="65282-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

