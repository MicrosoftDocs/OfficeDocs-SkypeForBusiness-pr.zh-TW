---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 一般來說，通訊錄會與您的其他拓撲一起遷移。 不過，如果您在舊版環境中自訂下列各項，可能需要執行一些遷移後步驟：
ms.openlocfilehash: 73c491a538e6bce95779533b88513321c674f018
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813601"
---
# <a name="migrate-address-book"></a>移轉通訊錄

一般來說，通訊錄會與您的其他拓撲一起遷移。 不過，如果您在舊版環境中自訂下列各項，可能需要執行一些遷移後步驟： 

- 已自訂通訊錄正常化規則。

- 已將**UseNormalizationRules**參數的預設值變更為 False。 


 **通訊錄正常化規則**

如果您在舊版環境中自訂通訊錄正常化規則，則必須將自訂規則遷移至您的試驗區。 如果您沒有自訂通訊錄正常化規則，您就無法針對通訊錄服務進行任何遷移。 商務用 Skype Server 2019 的預設正常化規則與舊版安裝的預設規則相同。 遵循本節稍後的程式，以遷移自訂的正常化規則。

> [!NOTE]
> 如果您的組織使用遠端通話控制，且您已自訂通訊錄正常化規則，您必須先執行本主題中的程式，才能使用遠端通話控制。 程式需要 RTCUniversalServerAdmins 群組或對等許可權的成員資格。 

 **UseNormalizationRules 設為 False**

如果您將**UseNormalizationRules**的值設為 False，讓使用者可以在 Active Directory 網域服務中定義的電話號碼，而不需要商務用 Skype Server 2019 套用正常化規則，您必須將**UseNormalizationRules**和**IgnoreGenericRules**參數設定為 True。 遵循本節稍後的程式，將這些參數設定為 True。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>遷移通訊錄自訂的正常化規則

1. 在通訊錄共用資料夾的根目錄中尋找 Company_Phone_Number_Normalization_Rules .txt 檔案，然後將其複製到商務用 Skype Server 2019 試驗區中的通訊錄共用資料夾的根目錄。

    > [!NOTE]
    > 範例通訊錄正常化規則已經安裝在您的 ABS 網頁元件檔案目錄中。 路徑是 **$installedDriveLetter： \Program Files\Microsoft 商務用 Skype Server 2019 \ Web Components\Address 簿 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules .txt**。 您可以將此檔案複製並重新命名為**Company_Phone_Number_Normalization_Rules**為通訊錄共用資料夾的根目錄。 例如，在 **$serverX**中共用通訊錄，路徑會類似： ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**。 

2. 使用文字編輯器（例如記事本）來開啟 Company_Phone_Number_Normalization_Rules .txt 檔案。

3. 在商務用 Skype Server 2019 中，某些類型的專案將無法正常運作。 在檔案中查看此步驟中描述的專案類型，視需要進行編輯，然後將變更儲存到您的試驗區中的通訊錄共用資料夾。

    包含所需空格或標點符號的字串會導致正常化規則失敗，因為這些字元會從輸入到正常化規則的字串中去除。 如果您有包含所需空格或標點符號的字串，您必須修改字串。 例如，下列字串將導致正常化規則失敗：

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    下列字串不會導致正常化規則失敗：

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>若要將 UseNormalizationRules 和 IgnoreGenericRules 設定為 true

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 商務用 skype server 2019**]，然後按一下 [**商務用 skype server 管理命令**介面]。

2. 請執行下列其中一項操作：

   - 如果您的部署只包含商務用 Skype Server 2019，請在全域層級執行下列 Cmdlet，將**UseNormalizationRules**和**IgnoreGenericRules**的值變更為 True： 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 如果您的部署包含商務用 Skype Server 2019 與舊版安裝的組合，請執行下列 Cmdlet，並將它指派給拓撲中的每個商務用 Skype Server 2019 池：

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. 等到中央管理儲存區複製在所有的池中進行。

4. 修改手機正常化規則檔案 "Company_Phone_Number_Normalization_Rules .txt"，以供您的部署清除內容。 檔案位於每個商務用 Skype Server 2019 池的檔案共用位置。 如果檔案不存在，請建立名為「Company_Phone_Number_Normalization_Rules .txt」的空檔案。

5. 針對所有前端池，請等候幾分鐘，以讀取新檔案。

6. 針對您部署中的每個商務用 Skype Server 2019 池執行下列 Cmdlet：

   ```PowerShell
   Update-CsAddressBook
   ```


