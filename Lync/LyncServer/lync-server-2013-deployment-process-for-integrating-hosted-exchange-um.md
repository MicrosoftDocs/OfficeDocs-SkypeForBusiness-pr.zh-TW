---
title: Lync Server 2013：整合主控 Exchange UM 的部署程式
description: Lync Server 2013：整合主控 Exchange UM 的部署程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542609"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>整合主控 Exchange UM 與 Lync Server 2013 的部署程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

若要有效規劃整合 Lync Server 2013 與主控 Exchange 整合通訊 (UM) ，必須考慮下列事項：

  - 整合 Lync Server 2013 與主控 Exchange UM 的必要條件

  - 整合過程中所需的步驟

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>與主控 Exchange UM 整合的部署必要條件

在您開始進行整合程式之前，您必須已部署 Lync Server 2013 (，至少要有一個前端集區或 Standard Edition server) 、Edge Server，以及 Lync 2013 或 Lync 2010 用戶端。

</div>

<div>

## <a name="integration-process"></a>整合處理常式

下表提供主控 Exchange UM 整合處理常式的概述。 如需部署步驟的詳細資訊，請參閱部署檔中的在 [主控 EXCHANGE UM 上提供 Lync Server 2013 使用者語音信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) 。


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
<th>權利和許可權</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定 Edge Server。</p></td>
<td><ol>
<li><p>設定同盟的 Edge Server。</p></li>
<li><p>手動將資料複製到 Edge Server。</p></li>
<li><p>在 Edge Server 上設定裝載提供者。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">將 Edge Server 設定為與主控 Exchange UM 整合</a></p></td>
</tr>
<tr class="even">
<td><p>設定主控語音信箱原則。</p></td>
<td><ol>
<li><p>請修改全域裝載語音信箱原則，或使用網站或 Per-User 範圍建立新的主控語音信箱原則。</p></li>
<li><p>針對 Per-User 範圍的原則，將原則指派給使用者或群組。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">在 Lync Server 2013 中管理主控語音信箱原則</a></p></td>
</tr>
<tr class="odd">
<td><p>為使用者啟用主控語音信箱。</p></td>
<td><ul>
<li><p>為信箱在主控 Exchange 服務上的使用者設定使用者帳戶。</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">在 Lync Server 2013 中啟用使用者的主控語音信箱功能</a></p></td>
</tr>
<tr class="even">
<td><p>設定主控的連絡人物件。</p></td>
<td><ol>
<li><p>為主控 Exchange UM 建立自動語音應答連絡人物件。</p></li>
<li><p>建立主控 Exchange UM 的訂戶存取連絡人物件。</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 若要建立、修改或移除連絡人物件，執行 New-CsExUmContact 的使用者、Set-CsExUmContact 或 Remove-CsExUmContact Cmdlet 必須具有儲存新連絡人物件之 Active Directory 組織單位的適當許可權。 執行 Grant-CsOUPermission Cmdlet，即可授與此權限。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">在 Lync Server 2013 中建立主控 Exchange UM 的連絡人物件</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

