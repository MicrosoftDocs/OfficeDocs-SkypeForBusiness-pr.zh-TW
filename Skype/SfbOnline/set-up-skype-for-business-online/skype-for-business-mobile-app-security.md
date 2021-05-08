---
title: 商務用 Skype 行動應用程式安全性
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '瞭解如何為使用者設定行動應用程式安全性。 '
ms.openlocfilehash: f600230574b8d16a0f7907b4484da8ffcca6124e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239630"
---
# <a name="skype-for-business-mobile-app-security"></a>商務用 Skype 行動應用程式安全性

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a>商務用 Skype用戶端安全性

本文涵蓋行動應用程式上商務用 Skype資訊。
  
|||||
|:-----|:-----|:-----|:-----|
||**使用者名稱/密碼** <br/> |**應用程式資料 (交談、 <br/> 連絡人清單、會議)** <br/> |**診斷記錄** <br/> |
|**Android** <br/> |我們會將認證資訊儲存在 Android 帳戶。 在將認證存到帳戶之前，我們也會先加密認證。 我們使用 **「AES/CBC/PKCS5Padding」** 演算法進行加密。 <br/> |我們會使用名為[sqlcipher](https://www.zetetic.net/sqlcipher/design/)SQL加密的資料庫。 我們在 CBC 模式中使用 256 位 AES 的預設演算法。 其餘的資料一直在資料庫檔案中加密，而且只會在 App 的易失性記憶體和通話堆疊內傳輸時未加密。 我們也會使用與使用者名稱和密碼加密相同的方法加密語音信箱 (這些檔案不會儲存在 DB) 。 語音信箱會暫時在磁片上取消加密，以允許播放。  <br/> |這項資訊未加密。  <br/> |
|**iOS** <br/> |我們不會加金鑰匙鏈中的使用者名稱/密碼。 不過，鑰匙鏈會自行加密。  <br/> |我們已在應用程式儲存空間的所有檔案上使用 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 資料保護標號。 這表示 App 儲存空間中的檔案會經過加密，直到使用者在裝置重新開機後第一次解除鎖定裝置。 <br/> |這項資訊未加密。  <br/> |
|**Windows Phone** <br/> |Windows Phone使用 DAPI (資料保護 API) 保護Windows密碼。 我相信所使用的加密方案是 AES。 Windows沒有提供設定金鑰大小的選項， (或配置) ，因此它是由DPAPI 提供。 它會使用裝置 TPM 保護使用者和裝置特有的金鑰。 請注意，DPAPI 金鑰並非應用程式專用。  <br/> |WP App 資料受 [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I 保護，例如 creds。 根據我們想要的詳細資料，App Data 的一些索引資訊會受 (非DPAPI) AES 加密保護，以避免資料被加密，因此我們可以在不解密的情況下進行尋找，而該金鑰則由DPAPI 保護。 如果緩存資料可以到達資料檔案夾，任何程式都可以從同一部手機讀取。 Windows加密無法防範沙箱入侵，只會嘗試外部存取。  <br/> |這項資訊未加密。  <br/> |
   
**注意：** 請參閱此 [公開檔，](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) 瞭解上述每個行動平臺提供的裝置釘釘強制執行功能
  
## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)

  
