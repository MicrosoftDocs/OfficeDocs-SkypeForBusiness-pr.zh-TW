---
title: 設定會議加入頁面
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 208f2d24d5617da703b04ea9888dd8b187f31476
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503320"
---
# <a name="configure-the-meeting-join-page"></a>設定會議加入頁面

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面便會偵測使用者電腦上是否已安裝 Lync 2013 用戶端。 若已安裝用戶端，將會開啟該用戶端，然後加入會議。 若未安裝用戶端，則預設會開啟2013版本的 Lync Web App。

如果您想要允許使用者加入使用 Office Communicator 2007 R2 或 Lync 2010 的會議，您可以修改會議加入頁面的行為。 這些設定選項已從 Lync Server 2013 控制台中移除，但您使用 CsWebServiceConfiguration Cmdlet 進行設定。

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>會議加入頁面的 CsWebServiceConfiguration 參數

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration 參數</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>若設為 True，使用 Lync 以外的用戶端應用程式加入會議的使用者，將有機會利用 Office Communicator 2007 R2 加入會議。 預設值為 False。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>此參數設為 True 時，就會自動擴充參加線上會議的其他選項 (例如 Office Communicator 2007 R2)，並且對使用者顯示。設為 False (預設值) 時，可使用這些選項，但使用者必須自行顯示選項清單。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面設定會議加入頁面

1.  啟動 Lync Server 2013 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet：
    
        Get-CsWebServiceConfiguration
    
    此 Cmdlet 會傳回 Web 服務設定。

3.  執行下列命令，並將參數設定為 True 或 False，這取決於您的喜好設定 (如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔) ：
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

