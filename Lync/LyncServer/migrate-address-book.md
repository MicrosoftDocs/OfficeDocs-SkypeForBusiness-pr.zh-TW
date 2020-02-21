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
ms.openlocfilehash: 42d28161eab03d494dd5ebb3771c0879dd3dbb99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>移轉通訊錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

一般而言，Lync Server 2010 通訊錄會移轉，以及您的拓樸的其餘部分。 不過，您可能需要執行一些步驟，移轉後，如果您在 Lync Server 2010 環境中自訂下列：

  - 將**PartitionbyOU** WMI 屬性設為通訊錄項目分組依組織單位 (OU)。

  - 自訂通訊錄正規化規則。

  - 變更**將 UseNormalizationRules**參數的預設值為 False。

**分組的通訊錄項目**

如果您將**PartitionbyOU** WMI 屬性設定為 True，針對每個 OU 建立通訊錄時，您需要的使用者和連絡人上設定**Msrtcsip-groupingid** Active Directory 屬性，如果您想要繼續進行分組通訊錄項目。 您可能想要限制的 Address Book 搜尋範圍的群組通訊錄項目。 若要使用**Msrtcsip-groupingid**屬性，撰寫指令碼，以填入屬性，將指派的相同值的所有使用者想要群組在一起。 例如，指派為 OU 中的所有使用者的單一值。

**通訊錄正規化規則**

如果您在 Lync Server 2010 環境中自訂通訊錄正規化規則，您必須將自訂的規則移轉至試驗集區。 如果您不沒有自訂通訊錄正規化規則，您必須將移轉的通訊錄服務則是 nothing。 Lync Server 2013 的預設正規化規則會與預設的 Lync Server 2010 規則相同。 遵循本節稍後將自訂的正規化規則的程序。

<div>


> [!NOTE]  
> 如果您的組織使用遠端呼叫控制，且您自訂通訊錄正規化規則，您必須執行此程序，本主題中後，您可以使用遠端呼叫控制即可。 程序需要相等的權限或 RTCUniversalServerAdmins 群組的成員資格。



</div>

**UseNormalizationRules 設為 False**

如果您將值**usenormalizationrules**設為 False，讓使用者可以使用電話號碼，而不需套用正規化規則的 Lync Server 2013 所定義的 Active Directory 網域服務中，您需要將**UseNormalizationRules**和**IgnoreGenericRules**參數設定為 True。 遵循本節稍後將這些參數設定為 True 的程序。

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>移轉通訊錄自訂正規化規則

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

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>將 UseNormalizationRules 和 IgnoreGenericRules 設為 true

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行下列其中一項動作：
    
      - 如果您的部署包含 Lync Server 2013，請在全域層級**UseNormalizationRules**和**IgnoreGenericRules**的值變更為 True 執行下列 cmdlet:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包含 Lync Server 2013 和 Lync Server 2010 或 Office Communications Server 2007 R2 的組合，請執行下列 cmdlet，並將其指派給拓撲中每個 Lync Server 2013 集區：
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待所有集區上發生的中央管理存放區複寫。

4.  修改電話正規化規則檔案中，「 公司\_電話\_號碼\_正規化\_Rules.txt 」，若要清除的內容部署。 檔案是在每個 Lync Server 2013 集區的檔案共用上。 如果檔案不存在，然後建立空的檔案，名為 「 公司\_電話\_號碼\_正規化\_Rules.txt 」。

5.  請稍候幾分鐘的所有前端集區讀取新檔案。

6.  在部署中的每個 Lync Server 2013 集區上執行下列 cmdlet:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

