---
title: Lync Server 2013：宣告應用程式的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2b1e9f8dd78b299a8e89e958f5b1c03acdffb7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中宣告應用程式的部署程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

本節概要說明部署宣告應用程式所需的步驟。 您必須先部署企業語音，然後才能設定宣告。 當您部署企業語音時，會安裝並啟用宣告應用程式所需的元件。

### <a name="announcement-deployment-process"></a>發佈部署程式

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>角色</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定宣告設定</p></td>
<td><ul>
<li><p>透過錄製及上傳音訊檔案或使用文字轉換語音（TTS）來建立公告。</p></li>
<li><p>在 [未指定的數位] 資料表中設定未指定的數位範圍，並將它們與適當的宣告建立關聯。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中建立公告</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">在 Lync Server 2013 中設定未指派號碼表</a></p></td>
</tr>
<tr class="even">
<td><p>確認您的宣告部署</p></td>
<td><p>透過聆聽宣告來測試，以確認您的設定如預期的那樣正常運作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">可選驗證 Lync Server 2013 中的宣告部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

