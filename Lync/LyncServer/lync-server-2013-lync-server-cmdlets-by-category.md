---
title: '依類別的 Lync Server 2013: Lync Server cmdlet'
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
ms.openlocfilehash: 8f9a93f338f6fd3367999a5879d222fc1e410b9a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a>依類別的 Lync Server 2013 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-09-20 個_

Microsoft Lync Server 2013 隨附特別設計用來允許系統管理員可以從命令列管理 Lync Server 的幾乎 550 指令程式。 您從 Lync Server 管理命令介面存取指令程式。 您可以直接從命令列擷取某個 Cmdlet 的說明，方法為輸入類似下列命令：

    Get-Help New-CsVoicePolicy -Full

上述命令會擷取 **New-CsVoicePolicy** Cmdlet 所有可用的說明。 請將 **New-CsVoicePolicy** 的部分換成您要擷取說明的 Cmdlet 名稱。

若要擷取 cmdlet 可用於管理 Microsoft Lync Server 2013 的完整清單，請在 Lync Server 管理命令介面命令提示字元處輸入下列命令：

    Get-Command * -Module Lync -CommandType cmdlet

如果您不確定需要哪個 Cmdlet，我們也提供 Cmdlet 及其說明主題的分類清單。您會發現某些 Cmdlet 出現在多個類別中，這是刻意的設計，因為它們適用於產品的多個區域。以下是類別清單：

<div>


> [!NOTE]
> Skype for Business cmdlet 參照已移至 docs.microsoft.com。 按一下下列連結將帶您前往 [新增 docs.microsoft.com] 頁面。 內容現在是透過 GitHub 開啟來源，並可供社群參與。 參與有興趣嗎？ 請參閱 「 讀我檔案中的儲存機制：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



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
<td><p><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013 中的使用者管理 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013 中的語音應用程式 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013 中的用戶端管理 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013 中的進階的 Enterprise Voice cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013 中的 IM 和目前狀態 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013 中的 PSTN 連線 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013 中的會議 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013 的電話和裝置 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013 中的基礎結構和部署 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013 中的移轉和共存指令程式</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013 中的安全性指令程式</a></p></td>
<td><p><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server 2013 中的 Lync Server 管理命令介面組態 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013 中的伺服器角色和服務 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013 中的行動性 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013 中的應用程式管理 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013 中 persistent Chat Server cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-federation-and-external-access-cmdlets.md">同盟和 Lync Server 2013 中的外部存取 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013 中的集中式的記錄 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013 中的 Enterprise Voice cmdlet</a></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server PowerShell 部落格](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

