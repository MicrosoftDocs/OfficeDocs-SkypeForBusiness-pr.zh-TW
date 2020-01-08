---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dff13c31ecf203d6e6e4b60c22a3792475e403f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>移轉通訊錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

**遷移通訊錄自訂的正常化規則**

1.  尋找通訊錄\_共用\_資料夾\_根目錄\_中的公司電話號碼正規化規則 .Txt 檔案，並將其複製到 Lync Server 2013 試驗區中通訊錄共用資料夾的根目錄。
    
    <div>
    

    > [!NOTE]  
    > 範例通訊錄正常化規則已經安裝在您的 ABS 網頁元件檔案目錄中。 路徑是<STRONG>$installedDriveLetter： \Program Files\Microsoft Lync Server 2013 \ Web Components\Address 書籍 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules .txt、</STRONG>。 您可以將此檔案複製並重新&nbsp;命名為<STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;為通訊錄共用資料夾的根目錄。 例如，在<STRONG>$serverX</STRONG>中共用通訊錄，&nbsp;路徑會類似： <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。

    
    </div>

2.  使用文字編輯器（例如記事本）來開啟\_公司電話\_號碼\_正常化\_規則 .txt 檔案。

3.  在 Lync Server 2013 中，某些類型的專案將無法正常運作。 在檔案中查看此步驟中描述的專案類型，視需要進行編輯，然後將變更儲存到您的試驗區中的通訊錄共用資料夾。
    
    包含所需空格或標點符號的字串會導致正常化規則失敗，因為這些字元會從輸入到正常化規則的字串中去除。 如果您有包含所需空格或標點符號的字串，您必須修改字串。 例如，下列字串將導致正常化規則失敗：
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    下列字串不會導致正常化規則失敗：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

