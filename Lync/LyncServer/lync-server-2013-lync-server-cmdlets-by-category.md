---
title: Lync Server 2013：依類別分類的 Lync Server Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 107a6a2094537c6937ae401f68807b494634f75f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525050"
---
# <a name="lync-server-2013-cmdlets-by-category"></a>Lync Server 2013 Cmdlet （按類別）

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-09-20_

Microsoft Lync Server 2013 隨附幾乎 550 Cmdlet，可讓系統管理員從命令列管理 Lync Server。 您可以從 Lync Server 管理命令介面存取 Cmdlet。 您可以直接從命令列擷取某個 Cmdlet 的說明，方法為輸入類似下列命令：

    Get-Help New-CsVoicePolicy -Full

上述命令會擷取 **New-CsVoicePolicy** Cmdlet 所有可用的說明。 請將 **New-CsVoicePolicy** 的部分換成您要擷取說明的 Cmdlet 名稱。

若要取得可用於管理 Microsoft Lync Server 2013 的完整 Cmdlet 清單，請在 Lync Server 管理命令介面命令提示字元處，輸入下列命令：

    Get-Command * -Module Lync -CommandType cmdlet

如果您不確定需要哪個 Cmdlet，我們也提供 Cmdlet 及其說明主題的分類清單。您會發現某些 Cmdlet 出現在多個類別中，這是刻意的設計，因為它們適用於產品的多個區域。以下是類別清單：

<div>


> [!NOTE]
> 商務用 Skype Cmdlet 參考已移至 docs.microsoft.com。 按一下下列連結將會帶您前往 [新增 docs.microsoft.com] 頁面。 內容現在已開啟，且可透過 GitHub 進行社區貢獻。 對共同作業感興趣？ 請參閱下列位置的讀我檔案： <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

<div>

## <a name="in-this-section"></a>本章節內容


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 中的使用者管理 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 中的語音應用程式 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 中的用戶端管理 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 中的高級 Enterprise Voice Cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 中的 IM 和目前狀態 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 中的 PSTN 連線 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 中的會議 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 中的電話和裝置 Cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 中的基礎結構和部署 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 中的遷移和共存 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 中的安全性 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync server 2013 中的 lync Server 管理命令介面設定 Cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 中的伺服器角色和服務 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 中的行動性 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 中的應用程式管理 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 中的 Persistent Chat Server Cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013 中的同盟與外部訪問 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 中的集中式記錄 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 中的 Enterprise Voice Cmdlet</a></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server PowerShell 的博客](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

