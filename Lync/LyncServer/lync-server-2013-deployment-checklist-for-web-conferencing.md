---
title: Web 會議的 Lync Server 2013 部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d3825891fe6934699e310073825e50a4aee731
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 web 會議部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

與其他 Lync Server 2013 元件的部署一樣，部署 web 會議時，需要您使用拓撲產生器來建立及發佈併入會議的拓撲。

<div>

## <a name="deployment-sequence"></a>部署順序

您可以在部署初始拓撲時，或在部署至少一個前端集區或 Standard Edition server 之後，部署會議。

</div>

<div>

## <a name="conferencing-deployment-process"></a>會議部署程序

下表提供將會議部署至現有拓撲所需的步驟概觀。


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
<th>角色和群組成員資格</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安裝必備硬體和軟體</strong></p></td>
<td><p>會議會在前端集區和 Standard Edition server 的前端伺服器上執行。 安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。</p>
<div>

> [!NOTE]  
> Lync Server 2013 使用 Office Web Apps 與 Office Web apps Server 來處理 PowerPoint 簡報的共用及呈現。 如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱設定<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps server 與 Lync server 2013 的整合</A>。


</div></td>
<td><p>為本機系統管理員成員之網域使用者</p></td>
<td><p>支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></p>
<p>支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></p>
<p>在規劃檔中<a href="lync-server-2013-determining-your-system-requirements.md">決定 Lync Server 2013 的系統需求</a>。</p>
<p>規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013</a>中封存的技術需求。</p></td>
</tr>
<tr class="even">
<td><p><strong>建立適當的內部拓撲以支援會議</strong></p></td>
<td><p>執行拓撲產生器，將會議新增至拓撲，然後發行拓撲。</p></td>
<td><p>定義拓撲，須以本機使用者群組成員帳戶進行</p>
<p>若要發行拓撲，則為 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，且具有「完全控制」 (許可權的檔案共用上的「讀取/寫入/修改」) ，以用於 Lync Server 2013 file store (，拓撲產生器可以設定必要的 Dacl) </p></td>
<td><p>在部署檔中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">定義及設定 Lync Server 2013 拓撲</a>產生器中的拓撲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>設定會議原則及支援</strong></p></td>
<td><p>使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定會議設定。</p></td>
<td><p>RTCUniversalServerAdmins 群組 ( Windows PowerShell 只) 或指派使用者至 [] 或 [CSAdministrator] 角色</p></td>
<td><p>Operations 檔中的<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</a>。</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 現在包括**MaxUploadFileSizeMb**設定，它會限制在會議期間可上傳的檔案大小。 此設定的預設值為 500 MB。 您可以使用**Set-CsConferencingConfiguration** Cmdlet 來調整**MaxUploadFileSizeMb** 。

**MaxUploadFileSizeMb**不會限制 Lync Web App 的檔案上傳設定。 Lync Web App 的檔案大小上傳限制設定為大約30MB，且由 IIS web.config 檔案：/DataCollabWeb/Int \[ Ext \] /Handler/web.config 所控制。若要設定 Lync Web App 的檔案大小上傳限制，請更新， `maxRequestLength` 並 `maxAllowedContentLength` 在 web.config 檔中，如下所示。

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

您必須更新每一部前端伺服器的 web.config 檔案。

</div>

</div>

<span> </span>

</div>

</div>

</div>

