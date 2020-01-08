---
title: 移除封存伺服器關聯
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ab171493890c610e0f11b7cd124c7c2e1c600c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a>移除封存伺服器關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

若要移除封存伺服器，您需要變更或清除相關聯的 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的相依性。 您可以編輯 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的屬性，以移除相依性。 在您清除相依性並刪除拓撲建立器中的伺服器之後，系統會通知您在拓撲建立器中相關聯的資料庫存放物件也會被刪除。

<div>

## <a name="to-remove-the-archiving-server-association"></a>移除存檔伺服器關聯

1.  開啟 Lync Server 2013 前端伺服器，然後開啟 [拓撲建立器]。

2.  流覽至 Lync Server 2010 節點。

3.  在拓撲建立器中，根據存檔伺服器的定義位置，展開 [**企業版前端池**]、[**標準版前端伺服器**] 或 [**分支網站**]。

4.  如果您有關聯的 Survivable 分支伺服器，請展開 [**分支網站**]，展開分支網站名稱，然後展開 [ **Survivable 分支裝置**]。
    
    <div>
    

    > [!NOTE]  
    > 使用者介面中的<STRONG>Survivable 分支裝置</STRONG>同時適用于 Survivable 分支伺服器和 Survivable 分支裝置。

    
    </div>

5.  以滑鼠右鍵按一下與封存伺服器相關聯的 [池]、[伺服器] 或 [裝置]，然後按一下 [**編輯屬性**]。

6.  在 **[編輯屬性**]**的 [一般**] 底下的 [**關聯**] 底下，清除 [關聯**存檔伺服器**] 核取方塊，然後按一下 **[確定]**。

7.  針對與您要移除之存檔伺服器相關聯的任何其他池、伺服器或裝置，重複上述步驟。

8.  以滑鼠右鍵按一下 [封存伺服器]，然後按一下 [**刪除**]。

9.  在 [**刪除相依儲存區**] 中，按一下 **[確定]**。

10. 發佈拓撲，檢查 [複製狀態]，然後視需要執行 Lync Server 部署嚮導。

</div>

</div>

<span> </span>

</div>

</div>

</div>

