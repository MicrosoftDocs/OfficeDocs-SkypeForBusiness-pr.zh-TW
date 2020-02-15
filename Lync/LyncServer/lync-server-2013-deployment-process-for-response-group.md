---
title: Lync Server 2013： 部署程序的回應群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc249ec8df233e6c22c9d5c1b54b81e23c5a173
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中的回應群組部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 09 月 27 日_

本章節提供階段和部署的回應群組應用程式的相關步驟的概觀。

### <a name="response-group-deployment-process"></a>回應群組部署程序

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
<th>權限</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>安裝回應群組應用程式</p></td>
<td><p>回應群組應用程式已安裝並啟用根據預設，當您部署企業語音。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">部署 Lync Server 2013 中的 Enterprise Voice</a></p></td>
</tr>
<tr class="even">
<td><p>回應群組安裝的元件</p></td>
<td><p>Lync Server cmdlet、 Lync Server 控制台中，回應群組組態工具、 代理的登入與登出主控台及回應群組用戶端 Web 服務安裝 Web 服務的一部分。 當您部署的 Enterprise Edition 集區或 Standard Edition server 已安裝 web 服務。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>啟用使用者的 Lync 2013 及 Enterprise voice</p></td>
<td><p>讓使用者擔任 Lync 伺服器和 Enterprise Voice 的代理程式。 您可以將其新增至代理程式群組之前，必須啟用使用者。 一般而言，使用者已啟用 Lync Server Enterprise Edition 或 Standard Edition server 部署期間。 使用者在 Enterprise Voice 部署期間啟用 Enterprise Voice。</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">停用或重新啟用 Lync Server 2013 的使用者帳戶</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">啟用使用者的 Lync Server 2013 中的 Enterprise Voice</a></p></td>
</tr>
<tr class="even">
<td><p>建立和設定回應群組，其中包含代理人群組、 佇列及工作流程</p></td>
<td><ol>
<li><p>使用 Lync Server Control Panel 或 Lync Server 管理命令介面來執行下列動作：</p>
<ol>
<li><p>建立和設定代理人群組。</p></li>
<li><p>建立和設定佇列。</p></li>
</ol></li>
<li><p>（選用） 使用 Lync Server 管理命令介面來建立預先定義的回應群組營業時間與假日。</p></li>
<li><p>使用的回應群組組態工具或 Lync Server 管理命令介面來建立工作流程 （群組搜尋或互動語音回應 (IVR) 通話流程），包括自訂回應群組營業時間與假日。</p>
<div>

> [!NOTE]  
> 您可以透過 Lync Server Control Panel 存取回應群組組態工具。


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">建立回應群組代理群組 Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013 中建立回應群組佇列</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">（選用）Lync Server 2013 中的定義回應群組營業時間</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">（選用）Lync Server 2013 中的定義回應群組假日集</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">建立或修改 Lync Server 2013 中的工作流程</a></p></td>
</tr>
<tr class="odd">
<td><p>（選用）自訂應用程式層級設定</p></td>
<td><p>使用 Lync Server 管理命令介面自訂預設的等候音樂上保留設定、 預設的等候音樂上保留音訊檔案、 代理人回電寬限期以及來電內容設定。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">管理 Lync Server 2013 中的應用程式層級回應群組設定</a></p></td>
</tr>
<tr class="even">
<td><p>（選用）委派管理回應群組</p></td>
<td><p>將使用者指派 CsResponseGroupManager 角色委派的回應群組組態。 回應群組管理員則可以設定指派給他們的回應群組。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中角色型存取控制</a></p></td>
</tr>
<tr class="odd">
<td><p>確認回應群組部署</p></td>
<td><p>測試群組搜尋或互動語音回應系統工作流程自動答錄服務呼叫以確保您的設定，如預期般運作。</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

