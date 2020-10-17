---
title: 設定用戶端以進行移轉
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99a0b7bfead8f74e27d8539038cf768b1a85b72e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499560"
---
# <a name="configure-clients-for-migration"></a>設定用戶端以進行移轉

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-21_

本主題包含在遷移至 Lync Server 2013 之前，應採取的建議用戶端部署步驟。 您應該在 Office 通訊伺服器 2007 R2 上進行這些設定變更。 在遷移之前，請務必先執行這些步驟。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃用戶端和裝置](lync-server-2013-planning-for-clients-and-devices.md)。

<div>

## <a name="to-configure-clients-prior-to-migration"></a>在遷移之前設定用戶端

1.  在 (修復程式) 上部署最近的 Office 通訊伺服器 2007 R2 伺服器、用戶端及裝置更新：
    
      - [套用 Office 通訊伺服器 2007 R2 更新](apply-office-communications-server-2007-r2-updates.md)
    
      - [Communicator 2007 R2 累計更新套件的描述](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [取得裝置的軟體更新](https://go.microsoft.com/fwlink/?linkid=335809)

2.  在 Office 通訊伺服器 2007 R2 上，使用用戶端版本篩選，只允許安裝了最新更新的 Office 通訊伺服器 2007 R2 用戶端登入。

3.  在 Office 通訊伺服器 2007 R2 上，使用用戶端版本篩選功能封鎖 Lync Server 2013 用戶端登入。 依照設定 **用戶端版本篩選** 中所述的步驟 [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) ，新增下表所列的版本篩選器。 針對每個版本篩選，指派 action **區塊**。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>用戶端</th>
    <th>使用者代理程式標頭</th>
    <th>版本</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>Oc</p></td>
    <td><p>15 ...* **</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>NM-CWA-13-NO-VERSION</p></td>
    <td><p>5 ...* **</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4 ...* **</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

