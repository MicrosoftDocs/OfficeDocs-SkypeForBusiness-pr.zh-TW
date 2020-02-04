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
description: '瞭解如何為您的使用者設定行動應用程式安全性。 '
ms.openlocfilehash: c8fa54ffa738bcd69f8cf4a29a530b86c91a63c7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692858"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="b00f1-103">商務用 Skype 行動應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="b00f1-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="b00f1-104">商務用 Skype 用戶端安全性</span><span class="sxs-lookup"><span data-stu-id="b00f1-104">Skype for Business Client Security</span></span>

<span data-ttu-id="b00f1-105">本文涵蓋商務用 Skype Mobile App 的資料加密資訊。</span><span class="sxs-lookup"><span data-stu-id="b00f1-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="b00f1-106">**使用者名稱/密碼**</span><span class="sxs-lookup"><span data-stu-id="b00f1-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="b00f1-107">**App 資料（交談、<br/>連絡人清單、會議）**</span><span class="sxs-lookup"><span data-stu-id="b00f1-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="b00f1-108">**診斷記錄**</span><span class="sxs-lookup"><span data-stu-id="b00f1-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="b00f1-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="b00f1-109">**Android**</span></span> <br/> |<span data-ttu-id="b00f1-110">我們會在 Android 帳戶中儲存認證資訊。</span><span class="sxs-lookup"><span data-stu-id="b00f1-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="b00f1-111">在將認證儲存到帳戶之前，我們也會將其加密。</span><span class="sxs-lookup"><span data-stu-id="b00f1-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="b00f1-112">我們使用 " **AES/CBC/PKCS5Padding** " 演算法進行加密。</span><span class="sxs-lookup"><span data-stu-id="b00f1-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="b00f1-113">我們使用名為[sqlcipher](https://www.zetetic.net/sqlcipher/design/)的文件庫，儲存在加密的 SQL 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="b00f1-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="b00f1-114">我們在 CBC 模式中使用256位 AES 的預設演算法。</span><span class="sxs-lookup"><span data-stu-id="b00f1-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="b00f1-115">Rest 中的資料在資料庫檔案中總是經過加密，而且只會在應用程式的易失性記憶體和呼叫堆疊中遭到不加密的傳輸。</span><span class="sxs-lookup"><span data-stu-id="b00f1-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="b00f1-116">我們也會使用與使用者名稱和密碼加密相同的方法（不會儲存在資料庫中）來加密語音信箱檔案。</span><span class="sxs-lookup"><span data-stu-id="b00f1-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="b00f1-117">語音訊息在磁片上暫時未加密，以允許播放。</span><span class="sxs-lookup"><span data-stu-id="b00f1-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="b00f1-118">此資訊不會加密。</span><span class="sxs-lookup"><span data-stu-id="b00f1-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="b00f1-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="b00f1-119">**iOS**</span></span> <br/> |<span data-ttu-id="b00f1-120">我們不會在鑰匙圈中加密使用者名稱/密碼。</span><span class="sxs-lookup"><span data-stu-id="b00f1-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="b00f1-121">不過，鑰匙圈會自行加密。</span><span class="sxs-lookup"><span data-stu-id="b00f1-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="b00f1-122">我們已在應用程式儲存區中的所有檔案上使用[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)資料保護標誌。</span><span class="sxs-lookup"><span data-stu-id="b00f1-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="b00f1-123">這表示 app 儲存空間中的檔案會經過加密，直到使用者在裝置重新開機後第一次解除鎖定裝置為止。</span><span class="sxs-lookup"><span data-stu-id="b00f1-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="b00f1-124">此資訊不會加密。</span><span class="sxs-lookup"><span data-stu-id="b00f1-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="b00f1-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="b00f1-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="b00f1-126">Windows Phone 在 Windows 中使用 DPAPI （資料保護 API）來保護密碼。</span><span class="sxs-lookup"><span data-stu-id="b00f1-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="b00f1-127">我相信所使用的加密配置是 AES。</span><span class="sxs-lookup"><span data-stu-id="b00f1-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="b00f1-128">Windows 不會提供設定金鑰大小（或配置）的選項，所以這就是 DPAPI 提供的任何選項。</span><span class="sxs-lookup"><span data-stu-id="b00f1-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="b00f1-129">它會使用裝置 TPM 來保護特定于使用者和裝置的金鑰。</span><span class="sxs-lookup"><span data-stu-id="b00f1-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="b00f1-130">請注意，DPAPI 金鑰並不是應用程式專用的。</span><span class="sxs-lookup"><span data-stu-id="b00f1-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="b00f1-131">WP 應用程式資料是使用[DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I （例如憑據）加以保護。</span><span class="sxs-lookup"><span data-stu-id="b00f1-131">WP App Data is protected with [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, like the creds.</span></span> <span data-ttu-id="b00f1-132">根據我們所需的詳細資料量，應用程式資料的一些索引資訊受到保護（非 DPAPI） AES 加密來避免 salt，所以我們可以查詢而不需解密，而且該金鑰也會使用 DPAPI 加以保護。</span><span class="sxs-lookup"><span data-stu-id="b00f1-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="b00f1-133">您可以從同一個手機讀取任何程式的快取資料，假設它可以存取資料檔案夾。</span><span class="sxs-lookup"><span data-stu-id="b00f1-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="b00f1-134">Windows 加密不會防止受到沙箱破壞，僅限外部存取嘗試。</span><span class="sxs-lookup"><span data-stu-id="b00f1-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="b00f1-135">此資訊不會加密。</span><span class="sxs-lookup"><span data-stu-id="b00f1-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="b00f1-136">**注意：** 請參閱[此公開檔](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)，以瞭解上述每個行動平臺上提供的裝置 pin 強制功能</span><span class="sxs-lookup"><span data-stu-id="b00f1-136">**Note:** Please refer to [this public documentation](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b00f1-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="b00f1-137">Related topics</span></span>
[<span data-ttu-id="b00f1-138">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="b00f1-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="b00f1-139">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="b00f1-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
