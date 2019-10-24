---
title: 商務用 Skype 行動裝置應用程式安全性
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
f1keywords: None
ms.custom:
- Setup
description: '瞭解如何為您的使用者設定行動應用程式安全性。 '
ms.openlocfilehash: 109fd6cb2ddccbc69ddae3e912506836ee49a399
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "37642437"
---
# <a name="skype-for-business-mobile-app-security"></a>商務用 Skype 行動裝置應用程式安全性

## <a name="skype-for-business-client-security"></a>商務用 Skype 用戶端安全性

本文涵蓋商務用 Skype Mobile App 的資料加密資訊。
  
|||||
|:-----|:-----|:-----|:-----|
||**使用者名稱/密碼** <br/> |**App 資料（交談、<br/>連絡人清單、會議）** <br/> |**診斷記錄** <br/> |
|**Android** <br/> |我們會在 Android 帳戶中儲存認證資訊。 在將認證儲存到帳戶之前，我們也會將其加密。 我們使用 " **AES/CBC/PKCS5Padding** " 演算法進行加密。 <br/> |我們使用名為[sqlcipher](https://www.zetetic.net/sqlcipher/design/)的文件庫，儲存在加密的 SQL 資料庫中。 我們在 CBC 模式中使用256位 AES 的預設演算法。 Rest 中的資料在資料庫檔案中總是經過加密，而且只會在應用程式的易失性記憶體和呼叫堆疊中遭到不加密的傳輸。 我們也會使用與使用者名稱和密碼加密相同的方法（不會儲存在資料庫中）來加密語音信箱檔案。 語音訊息在磁片上暫時未加密，以允許播放。  <br/> |此資訊不會加密。  <br/> |
|**且** <br/> |我們不會在鑰匙圈中加密使用者名稱/密碼。 不過，鑰匙圈會自行加密。  <br/> |我們已在應用程式儲存區中的所有檔案上使用[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)資料保護標誌。 這表示 app 儲存空間中的檔案會經過加密，直到使用者在裝置重新開機後第一次解除鎖定裝置為止。 <br/> |此資訊不會加密。  <br/> |
|**Windows Phone** <br/> |Windows Phone 在 Windows 中使用 DPAPI （資料保護 API）來保護密碼。 我相信所使用的加密配置是 AES。 Windows 不會提供設定金鑰大小（或配置）的選項，所以這就是 DPAPI 提供的任何選項。 它會使用裝置 TPM 來保護特定于使用者和裝置的金鑰。 請注意，DPAPI 金鑰並不是應用程式專用的。  <br/> |WP 應用程式資料是使用[DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I （例如憑據）加以保護。 根據我們所需的詳細資料量，應用程式資料的一些索引資訊受到保護（非 DPAPI） AES 加密來避免 salt，所以我們可以查詢而不需解密，而且該金鑰也會使用 DPAPI 加以保護。 您可以從同一個手機讀取任何程式的快取資料，假設它可以存取資料檔案夾。 Windows 加密不會防止受到沙箱破壞，僅限外部存取嘗試。  <br/> |此資訊不會加密。  <br/> |
   
**注意：** 請參閱[此公開檔](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)，以瞭解上述每個行動平臺上提供的裝置 pin 強制功能
  
## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)

  
 
