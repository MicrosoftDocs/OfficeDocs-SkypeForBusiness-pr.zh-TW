---
title: Lync Server 2013 會議的技術需求
description: Lync Server 2013 會議的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3b787d84288d789cd0d824081439004f19327e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577119"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-25_

針對 Lync Server 2013，電話撥入式會議、A/V 會議、立即訊息 (IM) 會議和 web 會議功能一定會在前端伺服器上執行。

本節將詳細說明這些伺服器的硬體和軟體需求，以及支援的組合。

電話撥入式會議是一項包含許多不同元件的功能。 有些元件是電話撥入式會議所特有的，有些則是企業語音元件。 本節說明電話撥入式會議專用元件的需求。 如需有關轉送伺服器和公用交換電話網路 (PSTN) 閘道需求的詳細資訊，請參閱規劃檔中的 [lync server 2013](lync-server-2013-mediation-server-component.md) 和中繼 [2013 伺服器的元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md) 中的轉送伺服器元件。

<div>

## <a name="hardware-requirements"></a>硬體需求

因為 web 會議和 A/V 會議會與前端伺服器組合，所以伺服器的硬體需求與前端伺服器的需求相同。 如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。 電話撥入式會議所需的下列元件也具有與前端伺服器相同的硬體需求：

  - 應用程式服務

  - Conferencing Attendant application

  - Conferencing Announcement application

前端伺服器的硬體需求與 Lync Server 2013 中的許多其他伺服器角色相同，如下表所示。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

因為 web 會議和 A/V 會議會與前端伺服器組合，所以伺服器軟體需求與前端伺服器的需求相同。 如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。

若為 web 會議，Lync Server 2013 也需要 Office Web Apps 和 Office Web Apps Server (（以前稱為 WAC Server) ）來處理 PowerPoint 簡報。 如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

在電話撥入式會議中，應用程式服務、會議應答應用程式和會議宣告應用程式與前端伺服器具有相同的作業系統需求。 如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。

會議應答應用程式和會議宣告應用程式需要 Windows Media Format Runtime 安裝在前端伺服器上。 您必須有 Windows Media Format Runtime 才能播放等候音樂、錄音名稱和提示所使用的 Windows Media Audio (WMA) 檔。 除了 Windows Server 2012 和 Windows Server 2012 R2 之外，Windows Media Format Runtime 會在您執行安裝程式時自動安裝為 Windows 桌面體驗的一部分，但您可能需要重新開機電腦。 因此建議您以 Windows Desktop Experience 的一部分安裝，其中包括 Windows Media Format Runtime。 Windows Server 2012 和 Windows Server 2012 R2 需要 Microsoft Media Foundation。

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>電話撥入式會議的連接埠需求

下表描述電話撥入式會議所使用的連接埠。如果您使用負載平衡器，務必針對將在集區中執行的任何應用程式所使用的連接埠設定負載平衡器。

這些連接埠為預設設定，可使用 **Set-CsApplicationServer** Cmdlet 予以變更。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

<div>


> [!NOTE]  
> 集區中同一個應用程式的所有執行個體都使用相同的 SIP 聆聽連接埠。



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>電話撥入式會議使用的連接埠

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>連接埠編號</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>用於 SIP 聆聽要求的會議值守應用程式</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>供會議宣告應用程式用於 SIP 聆聽要求</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>支援的電話撥入式會議用戶端

您可以使用下列用戶端，排程支援電話撥入式存取的內部部署會議：

  - 當您安裝 Lync 2013 或出席者時，會自動安裝 Lync 2013 (的線上會議增益集) 

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>電話撥入式會議設定頁面需求

[電話撥入式會議設定] 頁面支援下表所述之作業系統和網頁瀏覽器的組合。

<div>


> [!NOTE]  
> 支援 32 位元和 64 位元版本的作業系統。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>支援的作業系統和網頁瀏覽器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>作業系統</th>
<th>網頁瀏覽器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac 作業系統</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>電話撥入式會議的音訊檔需求

Lync Server 2013 不支援自訂語音提示和音樂的電話撥入式會議。 不過，如果您有需要變更預設音訊檔的強有力的商務需求，請參閱 Microsoft 知識庫文章961177： [如何在 Microsoft Office 通訊伺服器 2007 R2 中自訂語音提示或音樂檔，以進行電話撥入音訊會議](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)。

您也可以使用 [Microsoft Lync Server 會議助理自訂語音提示](https://go.microsoft.com/fwlink/p/?linkid=396880) 管理公用程式，讓系統管理員可以取代當電話來電者加入具有自訂提示的 Lync 會議以提供不同會議輸入經驗時所使用的預設語音提示。 自訂語音提示可以安裝在執行 Lync Server 2010 或 Lync Server 2013 （Enterprise 或 Standard Edition）的伺服器上。

會議應答應用程式和會議宣告應用程式對於等候音樂、錄製名稱和音訊提示檔有下列需求：

  - Windows Media Audio (WMA) 檔案格式

  - 16 位元單聲道

  - 48 kbps 2-pass CBR (常數位元速率)

  - 語音層級為 -24DB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>電話撥入式會議的使用者需求

必須指派唯一的電話號碼或分機至電話撥入式會議使用者的帳戶。 此需求可支援電話撥入式會議期間的驗證。 企業使用者 (，也就是在組織內具有 Active Directory 網域服務認證和 Lync Server 帳戶的使用者) 輸入他們的電話號碼 (或分機) ，以及個人識別碼 (PIN) ，以驗證的使用者的身分撥打會議。

</div>

</div>

<span> </span>

</div>

</div>

</div>

