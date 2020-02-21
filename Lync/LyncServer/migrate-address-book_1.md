---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e68dbe4db6ee9ac6b9bd758b23a575089019f6c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>移轉通訊錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

**移轉通訊錄自訂正規化規則**

1.  尋找公司\_電話\_號碼\_正規化\_Rules.txt 檔案通訊錄共用資料夾的根目錄中，並將它複製到 Lync Server 2013 試驗集區中通訊錄共用資料夾的根目錄。
    
    <div>
    

    > [!NOTE]  
    > 範例通訊錄正規化規則已安裝在您 ABS Web 元件的檔案目錄中。 路徑是<STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013\Web Components\Address 通訊錄 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt，</STRONG>。 要複製此檔案，然後重新命名為&nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;至通訊錄共用的資料夾的根目錄。 例如，通訊錄共用<STRONG>$serverX</STRONG>，&nbsp;路徑會類似： <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。

    
    </div>

2.  使用文字編輯器，例如 「 記事本 」，若要開啟 [公司\_電話\_號碼\_正規化\_Rules.txt 檔案。

3.  Lync Server 2013 中，某些類型的項目將無法正確運作。 查看的這個步驟中所述的項目類型的檔案，視需要編輯這些，將變更儲存至試驗集區中通訊錄共用資料夾。
    
    包含必要的空白字元或標點符號原因正規化規則失敗，因為這些字元會移除超出輸入正規化規則的字串的字串。 如果您有包含必要的空白字元或標點符號的字串，您要修改的字串。 例如，下列字串會導致正規化規則失敗：
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    下列字串將不會導致正規化規則失敗：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

