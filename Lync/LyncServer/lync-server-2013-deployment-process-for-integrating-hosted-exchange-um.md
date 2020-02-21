---
title: Lync Server 2013： 部署程序的整合主控 Exchange UM
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
ms.openlocfilehash: dfd58efd994e7034253fd3314e66d956e3259bcb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>部署程序的整合主控 Exchange UM 與 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-25_

整合 Lync Server 2013 與裝載 Exchange 整合通訊 (UM) 的有效地規劃，需要考慮下列：

  - 與裝載 Exchange UM 整合 Lync Server 2013 的必要條件

  - 整合過程所需的步驟

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>與裝載 Exchange UM 整合的部署先決條件

您可以開始整合程序之前，您必須已部署 Lync Server 2013 （在最低限度下，前端集區或 Standard Edition server）、 Edge Server 和 Lync 2013 或 Lync 2010 用戶端。

</div>

<div>

## <a name="integration-process"></a>整合程序

下表提供主控 Exchange UM 整合程序的概觀。 如需部署步驟的詳細資訊，請參閱部署文件中[提供 Lync Server 2013 使用者語音上裝載的 Exchange UM 的信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)。


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
<th>權利和權限</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定 Edge Server。</p></td>
<td><ol>
<li><p>設定同盟的 Edge Server。</p></li>
<li><p>以手動方式將資料複寫至 Edge Server。</p></li>
<li><p>在 Edge Server 上設定裝載提供者。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">設定 Edge Server 進行整合與裝載 Exchange UM</a></p></td>
</tr>
<tr class="even">
<td><p>設定裝載的語音信箱原則。</p></td>
<td><ol>
<li><p>修改全域裝載的語音信箱原則或是網站或個別使用者範圍建立新的裝載的語音信箱原則。</p></li>
<li><p>針對每個使用者範圍的原則，請將原則指派給使用者或群組。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">管理 Lync Server 2013 中的主控的語音信箱原則</a></p></td>
</tr>
<tr class="odd">
<td><p>啟用使用者的主控的語音信箱。</p></td>
<td><ul>
<li><p>設定使用者信箱位於裝載 Exchange 服務上的使用者帳戶。</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">啟用使用者的 Lync Server 2013 中裝載的語音信箱</a></p></td>
</tr>
<tr class="even">
<td><p>設定裝載連絡人物件。</p></td>
<td><ol>
<li><p>為裝載的 Exchange UM 建立自動語音應答連絡人物件。</p></li>
<li><p>為裝載的 Exchange UM 建立訂戶存取連絡人物件。</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 若要建立、 修改或移除連絡人物件，執行 New-csexumcontact，使用者 Set-csexumcontact 或移除 Get-csexumcontact cmdlet 必須正確的權限，以儲存新的連絡人物件所在的 Active Directory 組織單位。 執行 Grant-CsOUPermission Cmdlet，即可授與此權限。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">為裝載的 Exchange UM Lync Server 2013 中建立連絡人物件</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

