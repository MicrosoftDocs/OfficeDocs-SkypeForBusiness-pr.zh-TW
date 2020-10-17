---
title: Lync Server 2013：設定媒體埠範圍設定
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
ms.openlocfilehash: e13e491037346d9c3186a8f15aada949c46ac8df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502090"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定媒體埠範圍設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

媒體連接埠設定會顯著地影響用戶端效能，而應加以設定。 您可以使用 Lync Server 管理命令介面來設定這些設定。

### <a name="media-port-range-settings"></a>媒體連接埠範圍設定

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>設定</th>
<th>描述</th>
<th>Lync Server 管理命令介面 Cmdlet</th>
<th>Cmdlet 參數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>指定伺服器傳送的連接埠範圍是否應該供用戶端用於媒體和訊號。配合使用子機碼值 MinMediaPort 和 MaxMediaPort。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>指定用於媒體的起始連接埠號碼。與 MaxMediaPort 合併使用可指定連接埠範圍。建議最小範圍為 40 個連接埠。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (代表用於用戶端媒體的起始連接埠號碼)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>指定用於媒體的最高連接埠號碼。與 MinMediaPort 合併使用可指定連接埠範圍。建議最小範圍為 40 個連接埠。</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (表示可供用戶端媒體使用的連接埠總數；預設值為 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>設定媒體連接埠範圍設定

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet：
    
        Get-CsConferencingConfiguration
    
    此 Cmdlet 傳回會議設定。

3.  使用您要變更的參數和值來執行下列 Cmdlet (如需此 Cmdlet 之參數的詳細資訊，請參閱 Lync Server 管理命令介面檔) ：
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > 您可以建立特定站台的其他會議設定集。 請搭配使用 <STRONG>New- CsConferencingConfiguration</STRONG> Cmdlet 與站台身分識別。 當您建立站台的新會議設定時，站台設定的優先順序高於通用設定。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

