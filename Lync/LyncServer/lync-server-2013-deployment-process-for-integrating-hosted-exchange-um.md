---
title: Lync Server 2013：整合主控 Exchange UM 的部署程序
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
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>整合主控 Exchange UM 和 Lync Server 2013 的部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

整合 Lync Server 2013 與託管 Exchange 整合訊息（UM）的有效規劃，必須考慮下列事項：

  - 整合 Lync Server 2013 與託管 Exchange UM 的先決條件

  - 整合過程中所需的步驟

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>與託管 Exchange UM 整合的部署先決條件

您必須已部署 Lync Server 2013 （至少是前端池或標準版伺服器）、邊緣伺服器以及 Lync 2013 或 Lync 2010 用戶端，才能開始整合程式。

</div>

<div>

## <a name="integration-process"></a>整合程式

下表提供託管 Exchange UM 整合程式的概覽。 如需部署步驟的詳細資訊，請參閱在部署檔中[提供 Lync Server 2013 使用者 [託管 EXCHANGE UM] 上的語音信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)。


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
<th>權利和許可權</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定邊緣伺服器。</p></td>
<td><ol>
<li><p>設定同盟的 Edge Server。</p></li>
<li><p>手動將資料複製到 Edge 伺服器。</p></li>
<li><p>在 Edge 伺服器上設定主機服務提供者。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">將 Edge Server 設定為與主控 Exchange UM 整合</a></p></td>
</tr>
<tr class="even">
<td><p>設定託管的語音信箱原則。</p></td>
<td><ol>
<li><p>您可以修改全域託管的語音信箱原則，或建立新的託管語音信箱原則，以及網站或每個使用者的範圍。</p></li>
<li><p>針對每個使用者範圍的原則，將原則指派給 [使用者] 或 [群組]。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">在 Lync Server 2013 中管理裝載語音信箱原則</a></p></td>
</tr>
<tr class="odd">
<td><p>允許使用者使用託管的語音信箱。</p></td>
<td><ul>
<li><p>針對其信箱位於託管 Exchange 服務的使用者，設定使用者帳戶。</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">在 Lync Server 2013 中為使用者啟用主控語音信箱</a></p></td>
</tr>
<tr class="even">
<td><p>設定託管連絡人物件。</p></td>
<td><ol>
<li><p>建立託管 Exchange UM 的自動助理連絡人物件。</p></li>
<li><p>針對託管 Exchange UM 建立訂閱者存取連絡人物件。</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 若要建立、修改或移除連絡人物件，執行新的 CsExUmContact、Set CsExUmContact 或 Remove CsExUmContact Cmdlet 的使用者必須具備儲存新連絡人物件之 Active Directory 組織單位的正確許可權。 您可以執行授與 CsOUPermission Cmdlet 來授與此許可權。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">在 Lync Server 2013 中建立主控 Exchange UM 的聯絡人物件</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

