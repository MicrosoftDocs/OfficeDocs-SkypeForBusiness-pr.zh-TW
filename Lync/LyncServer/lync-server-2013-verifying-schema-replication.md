---
title: Lync Server 2013：驗證結構描述複寫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ea90012c116bb66caf16313d930c6f05db4413
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>在 Lync Server 2013 中驗證 Active Directory 結構描述複寫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

在執行林準備之前，請手動確認架構分區已複製。

<div>

## <a name="to-manually-verify-schema-replication"></a>手動驗證架構複製

1.  以企業系統管理員群組的成員身分登入網網域控制站。

2.  按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **adsi 編輯**]，以開啟 [adsi 編輯]。
    
    <div>
    

    > [!TIP]  
    > 或者，您可以從命令列執行<STRONG>adsiedit services.msc。</STRONG>

    
    </div>

3.  在 Microsoft 管理主控台（MMC）樹狀結構中，如果尚未選取，請按一下 [ **ADSI 編輯**]。

4.  在 [**動作**] 功能表上，按一下 **[連線至]**。

5.  在 [連線**設定**] 對話方塊中的 [**選取已知命名內容**] 底下，選取 [**架構**]，然後按一下 **[確定]**。

6.  在架構容器底下，搜尋 CN = ms-SIP-SchemaVersion。 如果此物件存在，且**rangeUpper**屬性的值為1150，且**rangeLower**屬性的值為3，則架構已成功更新並複製。 如果此物件不存在，或**rangeUpper**和**rangeLower**屬性的值不是指定的，則架構並未被修改或未複製。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中執行 Active Directory 架構準備](lync-server-2013-running-schema-preparation.md)  


[在 Lync Server 2013 中準備 Active Directory 結構描述](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

