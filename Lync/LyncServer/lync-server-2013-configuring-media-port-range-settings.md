---
title: Lync Server 2013：配置媒體埠範圍設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>在 Lync Server 2013 中配置媒體埠範圍設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

媒體埠範圍設定會顯著影響用戶端效能，應加以設定。 您可以使用 Lync Server 管理命令介面來設定這些設定。

### <a name="media-port-range-settings"></a>媒體埠範圍設定

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>正在</th>
<th>說明</th>
<th>Lync Server 管理命令介面 Cmdlet</th>
<th>Cmdlet 參數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>指定用戶端是否應該使用伺服器傳送的埠範圍來傳送媒體和傳送信號。 與 subvalues MinMediaPort 和 MaxMediaPort 搭配使用。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>指定要用於媒體的起始埠號碼。 與 MaxMediaPort 結合，以指定埠的範圍。 建議的最小範圍是40埠。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort （代表用戶端媒體要使用的起始埠號碼）</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>指定要用於媒體的最高埠數。 與 MinMediaPort 結合，以指定埠的範圍。 建議的最小範圍是40埠。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange （表示用戶端媒體可用的埠總數; 預設值為40）</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>若要設定媒體埠範圍設定

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet：
    
        Get-CsConferencingConfiguration
    
    這個 Cmdlet 會傳回會議設定。

3.  使用您要變更的參數和值來執行下列 Cmdlet （如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 管理命令介面檔）：
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > 您可以為特定網站建立其他的會議設定設定。 將<STRONG>CsConferencingConfiguration</STRONG> Cmdlet 與網站身分識別搭配使用。 當您為網站建立新的會議配置設定時，網站設定會優先于全域設定。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

