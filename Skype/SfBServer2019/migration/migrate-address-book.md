---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 一般說來，通訊錄會隨拓撲一起遷移。 不過，如果您自訂舊版環境中的下列步驟，您可能需要執行一些後續遷移步驟：
ms.openlocfilehash: 0ef965ef67393604e257049681a64ffb3c5b8fb1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599718"
---
# <a name="migrate-address-book"></a>移轉通訊錄

一般說來，通訊錄會隨拓撲一起遷移。 不過，如果您自訂舊版環境中的下列步驟，您可能需要執行一些後續遷移步驟： 

- 自訂通訊錄正常化規則。

- 將 **UseNormalizationRules** 參數的預設值變更為 False。 


 **通訊錄正常化規則**

如果您自訂舊版環境中的通訊錄正規化規則，您必須將自訂規則遷移至試驗集區。 如果您未自訂通訊錄正規化規則，則表示您沒有任何可遷移的通訊錄服務。 商務用 Skype Server 2019 的預設正常化規則與舊版安裝的預設規則相同。 依照本節稍後的程式，遷移自訂的正規化規則。

> [!NOTE]
> 如果您的組織使用遠端呼叫控制，且您自訂了通訊錄正規化規則，您必須先執行本主題中的程式，才能使用遠端呼叫控制。 此程式需要 RTCUniversalServerAdmins 群組或同等權利的成員資格。 

 **UseNormalizationRules 設定為 False**

如果您將 **UseNormalizationRules** 的值設為 False，讓使用者可以使用在 Active Directory 網域服務中定義的電話號碼，而不需要商務用 Skype Server 2019 套用正規化規則，您必須將 **UseNormalizationRules** 和 **IgnoreGenericRules** 參數設定為 True。 請依照本節稍後的程式將這些參數設定為 True。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>遷移通訊錄自訂正常化規則

1. 在 [通訊錄] 共用資料夾的根目錄中尋找 Company_Phone_Number_Normalization_Rules.txt 檔案，並將它複製到您商務用 Skype Server 2019 試驗集區中的通訊錄共用資料夾根目錄。

    > [!NOTE]
    > 您的 ABS 網頁元件檔案目錄中已安裝範例通訊錄正常化規則。 路徑為 **$installedDriveLetter： \Program Files\Microsoft 商務用 Skype Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**。 您可以將此檔案複製並重新命名為 **Company_Phone_Number_Normalization_Rules.txt** 通訊錄共用資料夾的根目錄。 例如， **$serverX** 中共用的通訊錄，該路徑會類似如下： **\\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**。 

2. 使用文字編輯器（例如記事本）來開啟 Company_Phone_Number_Normalization_Rules.txt 檔案。

3. 在商務用 Skype Server 2019 中，某些類型的專案將無法正確運作。 查看此步驟中所述之專案類型的檔案，視需要進行編輯，然後將變更儲存至試驗集區中的通訊錄共用資料夾。

    包含必要空格或標點符號的字串會導致正規化規則失敗，因為這些字元會從輸入到正規化規則的字串中去掉。 如果您有包含必要空格或標點符號的字串，您必須修改字串。 例如，下列字串會導致正規化規則失敗：

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    下列字串將不會導致正規化規則失敗：

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>若要將 UseNormalizationRules 和 IgnoreGenericRules 設定為 true

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft 商務用 Skype Server 2019**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 執行下列其中一項：

   - 如果您的部署只包含商務用 Skype Server 2019，請在全域層級執行下列 Cmdlet，以變更 **UseNormalizationRules** 的值，並將 **IgnoreGenericRules** 為 True： 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 如果您的部署包含商務用 Skype Server 2019 和舊版安裝的組合，請執行下列 Cmdlet，並將其指派給拓撲中的每個商務用 Skype Server 2019 集區：

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. 等候中央管理存放區的複寫在所有集區上進行。

4. 修改電話正規化規則檔案 "Company_Phone_Number_Normalization_Rules.txt"，以供您的部署清除內容。 檔案位於每個商務用 Skype Server 2019 集區的檔案共用。 如果檔案不存在，請建立名為 "Company_Phone_Number_Normalization_Rules.txt" 的空檔案。

5. 請等候幾分鐘，讓所有前端集區讀取新的檔案。

6. 在您部署中的每個商務用 Skype Server 2019 集區上執行下列 Cmdlet：

   ```PowerShell
   Update-CsAddressBook
   ```


