---
title: Lync Server 2013：刪除電話撥入式會議存取號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2559b8a3e053c02a6a67ccc17ab5a1f25b46a05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>刪除 Lync Server 2013 中的電話撥入式會議存取號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

請依照下列步驟刪除電話撥入式會議存取號碼。

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>刪除電話撥入式會議存取號碼

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]，然後按一下 [**撥入存取號碼**]。

4.  在頁面上，按一下清單中您要刪除的撥入號碼，按一下 [**編輯**]，然後按一下 [**刪除**]。

5.  按一下 [確定]****。

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除電話撥入式會議存取號碼

您可以使用 Windows PowerShell 和**CsDialInConferencingAccessNumber** Cmdlet 來刪除電話撥入式會議存取號碼。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>移除特定的電話撥入式會議存取號碼

  - 這個命令會刪除含身分識別 sip:RedmondDialInAccess@litwareinc.com 的電話撥入式會議存取號碼：
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>移除指派給特定區域的所有電話撥入式會議存取號碼

  - 這個命令會刪除與西北地方相關的所有電話撥入式會議存取號碼：
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>若要移除以主要語言為基礎的電話撥入式會議存取號碼

  - 這個命令會刪除所有以義大利文為主要語言的電話撥入式會議存取號碼：
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

如需詳細資訊，請參閱[Remove CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

