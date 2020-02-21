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
ms.openlocfilehash: 44fc32360fe7ffe1924fbc663709dd1f41cf4a36
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的宣告應用程式的部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

本節提供部署宣告應用程式的相關步驟的概觀。 設定宣告之前，您必須部署企業語音。 宣告應用程式所需的元件會安裝並啟用當您部署企業語音。

### <a name="announcement-deployment-process"></a>宣告部署程序

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>角色</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定宣告設定</p></td>
<td><ul>
<li><p>錄製及上傳音訊檔案，或是使用文字轉語音 (TTS)，以建立宣告。</p></li>
<li><p>設定未指派號碼表格中的未指派號碼範圍，並建立它們與適當宣告的關聯。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013 中建立的宣告</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">在 Lync Server 2013 中設定未指派號碼表</a></p></td>
</tr>
<tr class="even">
<td><p>驗證宣告部署</p></td>
<td><p>透過接聽宣告以驗證設定如預期運作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">（選用）確認 Lync Server 2013 中的宣告部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

