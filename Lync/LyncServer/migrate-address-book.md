---
title: 移轉通訊錄
description: 遷移通訊錄。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad6acd8cca58aa4e09e21b9b45cbdddec527b5f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579389"
---
# <a name="migrate-address-book"></a>移轉通訊錄

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

一般說來，Lync Server 2010 通訊錄會隨拓撲一起遷移。 不過，如果您在 Lync Server 2010 環境中自訂下列的後續遷移步驟，您可能需要執行一些後續遷移步驟：

  - 將 **PartitionbyOU** WMI 屬性設定成依組織單位 (OU) 群組通訊錄專案。

  - 自訂通訊錄正常化規則。

  - 將 **UseNormalizationRules** 參數的預設值變更為 False。

**群組通訊錄專案**

如果您將 **PartitionbyOU** WMI 屬性設定為 True，為每個 OU 建立通訊錄，如果您想要繼續群組通訊錄專案，則必須設定使用者和連絡人上的 **MsRTCSIP partitionbyou** Active Directory 屬性。 您可能想要群組通訊錄專案，以限制通訊錄搜尋的範圍。 若要使用 **MsRTCSIP partitionbyou** 屬性，請撰寫腳本，以填入屬性，並為您要一起群組的所有使用者指派相同的值。 例如，為 OU 中的所有使用者指派單一值。

**通訊錄正常化規則**

如果您已在 Lync Server 2010 環境中自訂通訊錄正規化規則，您必須將自訂規則遷移至試驗集區。 如果您未自訂通訊錄正規化規則，則表示您沒有任何可遷移的通訊錄服務。 Lync Server 2013 的預設正規化規則與 Lync Server 2010 的預設規則相同。 依照本節稍後的程式，遷移自訂的正規化規則。

<div>


> [!NOTE]  
> 如果您的組織使用遠端呼叫控制，且您自訂了通訊錄正規化規則，您必須先執行本主題中的程式，才能使用遠端呼叫控制。 此程式需要 RTCUniversalServerAdmins 群組或同等權利的成員資格。



</div>

**UseNormalizationRules 設定為 False**

如果您將 **UseNormalizationRules** 的值設為 False，讓使用者可以使用在 Active Directory 網域服務中定義的電話號碼，而不需要 Lync Server 2013 套用正規化規則，您必須將 **UseNormalizationRules** 和 **IgnoreGenericRules** 參數設定為 True。 請依照本節稍後的程式將這些參數設定為 True。

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>遷移通訊錄自訂正常化規則

1.  \_ \_ \_ \_ 在 [通訊錄] 共用資料夾的根目錄中尋找公司電話號碼正規化Rules.txt 檔案，並將它複製到 Lync Server 2013 試驗集區中的 [通訊錄共用資料夾] 根。
    
    <div>
    

    > [!NOTE]  
    > 您的 ABS 網頁元件檔案目錄中已安裝範例通訊錄正常化規則。 路徑為 <STRONG>$installedDriveLetter： \Program Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt，</STRONG>。 您可以將此檔案複製並重新命名為 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 通訊錄共用資料夾的根目錄。 例如， <STRONG>$serverX</STRONG>中共用的通訊錄， &nbsp; 該路徑會類似如下： <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。

    
    </div>

2.  使用文字編輯器（例如 [記事本]）開啟公司 \_ 電話號碼正規化 \_ \_Rules.txt 檔 \_ 。

3.  在 Lync Server 2013 中某些類型的專案將無法正確運作。 查看此步驟中所述之專案類型的檔案，視需要進行編輯，然後將變更儲存至試驗集區中的通訊錄共用資料夾。
    
    包含必要空格或標點符號的字串會導致正規化規則失敗，因為這些字元會從輸入到正規化規則的字串中去掉。 如果您有包含必要空格或標點符號的字串，您必須修改字串。 例如，下列字串會導致正規化規則失敗：
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    下列字串將不會導致正規化規則失敗：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>若要將 UseNormalizationRules 和 IgnoreGenericRules 設定為 true

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列其中一項：
    
      - 如果您的部署只包含 Lync Server 2013，請在全域層級執行下列 Cmdlet，將 **UseNormalizationRules** 和 **IgnoreGenericRules** 的值變更為 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包含 Lync Server 2013 和 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的組合，請執行下列 Cmdlet，並將其指派給拓撲中的每個 Lync Server 2013 集區：
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等候中央管理存放區的複寫在所有集區上進行。

4.  針對您的部署，修改電話正規化規則檔案「公司 \_ 電話 \_ 號碼正規化Rules.txt」 \_ \_ ，以清除內容。 檔位於每個 Lync Server 2013 集區的檔案共用上。 如果檔案不存在，請建立名為 "Company \_ Phone \_ Number 正規化 \_ \_Rules.txt" 的空檔案。

5.  請等候幾分鐘，讓所有前端集區讀取新的檔案。

6.  在您部署中的每個 Lync Server 2013 集區上執行下列 Cmdlet：
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

