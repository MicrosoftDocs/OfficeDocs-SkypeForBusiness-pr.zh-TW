---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>移轉通訊錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

一般來說，Lync Server 2010 通訊錄會與其他拓撲一起遷移。 不過，如果您在 Lync Server 2010 環境中自訂下列專案，可能需要執行一些遷移後步驟：

  - 將 [ **PartitionbyOU** WMI] 屬性設定為 [依組織單位（OU）群組通訊錄專案]。

  - 已自訂通訊錄正常化規則。

  - 已將**UseNormalizationRules**參數的預設值變更為 False。

**群組通訊錄專案**

如果您將**PartitionbyOU** WMI 屬性設定為 True，為每個 OU 建立通訊錄，您必須在使用者和連絡人上設定**msRTCSIP-GroupingId** Active Directory 屬性，才能繼續群組通訊錄專案。 您可能會想要將通訊錄專案分組，以限制通訊錄搜尋的範圍。 若要使用**msRTCSIP-GroupingId**屬性，請撰寫腳本來填入屬性，並為您要組成群組的所有使用者指派相同的值。 例如，為 OU 中的所有使用者指派單一值。

**通訊錄正常化規則**

如果您在 Lync Server 2010 環境中自訂通訊錄正常化規則，則必須將自訂規則遷移至您的試驗區。 如果您沒有自訂通訊錄正常化規則，您就無法針對通訊錄服務進行任何遷移。 Lync Server 2013 的預設正常化規則與 Lync Server 2010 的預設規則相同。 遵循本節稍後的程式，以遷移自訂的正常化規則。

<div>


> [!NOTE]  
> 如果您的組織使用遠端通話控制，且您已自訂通訊錄正常化規則，您必須先執行本主題中的程式，才能使用遠端通話控制。 程式需要 RTCUniversalServerAdmins 群組或對等許可權的成員資格。



</div>

**UseNormalizationRules 設為 False**

如果您將**UseNormalizationRules**的值設為 False，讓使用者可以在 Active Directory 網域服務中定義的電話號碼，而不需讓 Lync Server 2013 套用正常化規則，您必須將**UseNormalizationRules**和**IgnoreGenericRules**參數設定為 True。 遵循本節稍後的程式，將這些參數設定為 True。

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>遷移通訊錄自訂的正常化規則

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

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>若要將 UseNormalizationRules 和 IgnoreGenericRules 設定為 true

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  請執行下列其中一項操作：
    
      - 如果您的部署只包含 Lync Server 2013，請在全域層級執行下列 Cmdlet，將**UseNormalizationRules**和**IgnoreGenericRules**的值變更為 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的組合，請執行下列 Cmdlet，並將它指派給拓撲中的每個 Lync Server 2013 池：
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等到中央管理儲存區複製在所有的池中進行。

4.  針對您的部署，修改手機正常化規則\_檔案\_"\_公司\_電話號碼正規化規則 .txt"，以清除內容。 檔案位於每個 Lync Server 2013 池的檔案共用位置。 如果檔案不存在，請建立名為「\_公司電話\_號碼\_正常化\_Rules .txt」的空檔案。

5.  針對所有前端池，請等候幾分鐘，以讀取新檔案。

6.  在部署的每個 Lync Server 2013 池中執行下列 Cmdlet：
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

