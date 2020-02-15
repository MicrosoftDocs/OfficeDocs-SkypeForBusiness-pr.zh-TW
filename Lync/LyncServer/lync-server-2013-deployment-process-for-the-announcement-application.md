---
title: Lync Server 2013： 部署程序，宣告應用程式
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
ms.openlocfilehash: 55e0c65bfbbed55a8d7f9c3be4f7a586581c2307
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="59c69-102">Lync Server 2013 中的宣告應用程式的部署程序</span><span class="sxs-lookup"><span data-stu-id="59c69-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59c69-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="59c69-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="59c69-104">本節提供部署宣告應用程式的相關步驟的概觀。</span><span class="sxs-lookup"><span data-stu-id="59c69-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="59c69-105">設定宣告之前，您必須部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="59c69-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="59c69-106">宣告應用程式所需的元件會安裝並啟用當您部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="59c69-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="59c69-107">宣告部署程序</span><span class="sxs-lookup"><span data-stu-id="59c69-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59c69-108">階段</span><span class="sxs-lookup"><span data-stu-id="59c69-108">Phase</span></span></th>
<th><span data-ttu-id="59c69-109">步驟</span><span class="sxs-lookup"><span data-stu-id="59c69-109">Steps</span></span></th>
<th><span data-ttu-id="59c69-110">角色</span><span class="sxs-lookup"><span data-stu-id="59c69-110">Roles</span></span></th>
<th><span data-ttu-id="59c69-111">部署文件</span><span class="sxs-lookup"><span data-stu-id="59c69-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59c69-112">設定宣告設定</span><span class="sxs-lookup"><span data-stu-id="59c69-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="59c69-113">錄製及上傳音訊檔案，或是使用文字轉語音 (TTS)，以建立宣告。</span><span class="sxs-lookup"><span data-stu-id="59c69-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="59c69-114">設定未指派號碼表格中的未指派號碼範圍，並建立它們與適當宣告的關聯。</span><span class="sxs-lookup"><span data-stu-id="59c69-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c69-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="59c69-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="59c69-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="59c69-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="59c69-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="59c69-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="59c69-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="59c69-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="59c69-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="59c69-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="59c69-120"><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013 中建立的宣告</a></span><span class="sxs-lookup"><span data-stu-id="59c69-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="59c69-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">在 Lync Server 2013 中設定未指派號碼表</a></span><span class="sxs-lookup"><span data-stu-id="59c69-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c69-122">驗證宣告部署</span><span class="sxs-lookup"><span data-stu-id="59c69-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="59c69-123">透過接聽宣告以驗證設定如預期運作。</span><span class="sxs-lookup"><span data-stu-id="59c69-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c69-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">（選用）確認 Lync Server 2013 中的宣告部署</a></span><span class="sxs-lookup"><span data-stu-id="59c69-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

