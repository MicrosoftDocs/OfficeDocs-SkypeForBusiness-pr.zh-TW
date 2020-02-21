---
title: 'Lync Server 2013: Standard Edition server 的 DNS 需求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12a4d87f0ffa1ab7d6e857a40c2440d35d0b38aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>在 [Lync Server 2013 Standard Edition server 的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

本節說明 Standard Edition Server 部署所需的網域名稱系統 (DNS) 記錄。

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Standard Edition Server 的 DNS 記錄

下表指定 Lync Server 2013 Standard Edition server 部署的 DNS 需求。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>部署案例</th>
<th>DNS 需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition Server</p></td>
<td><p>一筆內部 A 記錄，用來將伺服器的完整網域名稱 (FQDN) 解析為 IP 位址。</p></td>
</tr>
<tr class="even">
<td><p>自動用戶端登入</p></td>
<td><p>每個支援的 SIP 網域，_sipinternaltls._tcp 的 SRV 記錄。&lt;網域&gt;透過對應的 FQDN，Standard Edition server 的驗證，並將登入的用戶端要求重新導向至連接埠 5061。 如需詳細資訊，請參閱<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS 需求的用戶端自動登入 Lync Server 2013 中</a>。</p></td>
</tr>
<tr class="odd">
<td><p>整合通訊 (UC) 裝置的裝置更新 Web 服務探索</p></td>
<td><p>一筆內部 A 記錄名稱 ucupdates-r2。&lt;SIP 網域&gt;，解析為 Standard Edition server 主控的裝置更新 Web 服務的 IP 位址。 在 UC 裝置已開啟，但尚未有使用者登入裝置的情況下，此 A 記錄會允許裝置去探索裝載著裝置更新 Web 服務的伺服器並取得更新。 否則，裝置會透過使用者首次登入時的頻內佈建取得伺服器資訊。 如需詳細資訊，請參閱作業文件中的<a href="lync-server-2013-device-update-web-service.md">Lync Server 2013 中的裝置更新 Web 服務</a>。</p></td>
</tr>
<tr class="even">
<td><p>支援 HTTP 流量的反向 Proxy</p></td>
<td><p>一筆外部 A 記錄，將外部 Web 伺服陣列 FQDN 解析為反向 Proxy 的外部 IP 位址。 用戶端和 UC 裝置會使用這個記錄來連線至反向 Proxy。 如需詳細資訊，請參閱規劃文件中的<a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 的判斷 DNS 需求</a>。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[DNS 需求的用戶端自動登入 Lync Server 2013 中](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[決定針對 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013 中的裝置更新 Web 服務](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

