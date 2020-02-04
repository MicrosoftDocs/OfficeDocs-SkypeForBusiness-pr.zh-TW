---
title: 適用于 web 會議的 Lync Server 2013 部署檢查清單
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
ms.openlocfilehash: 426f6419b2127a09dd3c758cdb7d6e418e6c4fc6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 的網路會議部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

隨著您其他 Lync Server 2013 元件的部署，部署 web 會議時，需要您使用拓撲建立器來建立併發布包含會議的拓撲。

<div>

## <a name="deployment-sequence"></a>部署順序

您可以在部署初始拓朴時，或在部署了至少一個前端池或標準版伺服器之後，部署會議。

</div>

<div>

## <a name="conferencing-deployment-process"></a>會議部署流程

下表提供將會議部署至現有拓撲所需的步驟的概覽。


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
<th>角色和群組成員資格</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安裝必備的硬體和軟體</strong></p></td>
<td><p>在前端伺服器和標準版伺服器中，在前端伺服器上執行會議。 除了安裝這些伺服器所需的其他硬體或軟體需求之外，它還沒有其他硬體或軟體需求。</p>
<div>

> [!NOTE]  
> Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 伺服器來處理 PowerPoint 簡報的共用和轉譯。 如需安裝及設定 Office Web Apps 伺服器的相關資訊，請參閱設定<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">與 Office Web Apps server 和 Lync Server 2013 的整合</A>。


</div></td>
<td><p>屬於本機管理員群組成員的網域使用者</p></td>
<td><p>支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></p>
<p>支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></p>
<p>在規劃檔中<a href="lync-server-2013-determining-your-system-requirements.md">判斷 Lync Server 2013 的系統需求</a>。</p>
<p>規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中的存檔技術需求</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>建立適當的內部拓朴以支援會議</strong></p></td>
<td><p>執行拓撲建立器，將會議新增至拓撲結構，然後發佈拓撲。</p></td>
<td><p>若要定義拓撲，該帳戶是 [本機使用者] 群組的成員</p>
<p>若要發佈拓朴，該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員，且在檔案共用上擁有 [完全控制] 許可權（讀取/寫入/修改），以用於 Lync Server 2013 檔案存放區（以便讓拓撲建立器能夠設定所需的 Dacl）</p></td>
<td><p>在 [部署] 檔中，在 [Lync Server 2013] 的 [拓撲建立器] 中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">定義及設定拓撲</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>設定會議原則及支援</strong></p></td>
<td><p>使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面] 來設定會議設定。</p></td>
<td><p>RTCUniversalServerAdmins 群組（僅限 Windows PowerShell）或將使用者指派至 [] 或 CSAdministrator 角色</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</a>在作業檔中。</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 現在包含 [ **MaxUploadFileSizeMb** ] 設定，可限制在會議期間可以上傳的檔案大小。 此設定的預設值為 500 MB。 您可以使用**CsConferencingConfiguration** Cmdlet 來調整**MaxUploadFileSizeMb** 。

**MaxUploadFileSizeMb**不會限制 Lync Web App 的 [檔案上傳] 設定。 Lync Web App 的檔案大小上傳限制是設定為 [大約 30MB]，且由 IIS web.config 檔案所控制：/DataCollabWeb/Int\[Ext\]/Handler/web.config。若要設定 Lync Web App 的檔案大小上傳限制， `maxRequestLength`請`maxAllowedContentLength`更新並放在 web.config 檔案中，如下所示。

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

您必須為每個前端伺服器更新 web.config 檔案。

</div>

</div>

<span> </span>

</div>

</div>

</div>

