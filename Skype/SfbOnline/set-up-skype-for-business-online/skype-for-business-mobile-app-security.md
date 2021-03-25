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
ms.openlocfilehash: d599542970cec5aa4206f29d3ff7fa27ce36e9a0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109949"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="08d1a-103">商務用 Skype 行動應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="08d1a-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="08d1a-104">商務用 Skype 用戶端安全性</span><span class="sxs-lookup"><span data-stu-id="08d1a-104">Skype for Business Client Security</span></span>

<span data-ttu-id="08d1a-105">本文涵蓋商務用 Skype 行動應用程式上的資料加密資訊。</span><span class="sxs-lookup"><span data-stu-id="08d1a-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="08d1a-106">**使用者名稱/密碼**</span><span class="sxs-lookup"><span data-stu-id="08d1a-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="08d1a-107">**應用程式資料 (交談 <br/> 、連絡人清單、會議)**</span><span class="sxs-lookup"><span data-stu-id="08d1a-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="08d1a-108">**診斷記錄**</span><span class="sxs-lookup"><span data-stu-id="08d1a-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="08d1a-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="08d1a-109">**Android**</span></span> <br/> |<span data-ttu-id="08d1a-110">我們會將認證資訊儲存在 Android 帳戶。</span><span class="sxs-lookup"><span data-stu-id="08d1a-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="08d1a-111">在將認證存到帳戶之前，我們也會先加密認證。</span><span class="sxs-lookup"><span data-stu-id="08d1a-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="08d1a-112">我們使用 **「AES/CBC/PKCS5Padding」** 演算法進行加密。</span><span class="sxs-lookup"><span data-stu-id="08d1a-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="08d1a-113">我們使用名為 [sqlcipher](https://www.zetetic.net/sqlcipher/design/)的文件庫儲存在加密的 SQL 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="08d1a-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="08d1a-114">我們在 CBC 模式中使用 256 位 AES 的預設演算法。</span><span class="sxs-lookup"><span data-stu-id="08d1a-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="08d1a-115">其餘的資料一直在資料庫檔案中加密，而且只會在 App 的易失性記憶體和通話堆疊內傳輸時未加密。</span><span class="sxs-lookup"><span data-stu-id="08d1a-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="08d1a-116">我們也會使用與使用者名稱和密碼加密相同的方法加密語音信箱 (這些檔案不會儲存在 DB) 。</span><span class="sxs-lookup"><span data-stu-id="08d1a-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="08d1a-117">語音信箱會暫時在磁片上取消加密，以便播放。</span><span class="sxs-lookup"><span data-stu-id="08d1a-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="08d1a-118">這項資訊未加密。</span><span class="sxs-lookup"><span data-stu-id="08d1a-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="08d1a-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="08d1a-119">**iOS**</span></span> <br/> |<span data-ttu-id="08d1a-120">我們不會加金鑰匙鏈中的使用者名稱/密碼。</span><span class="sxs-lookup"><span data-stu-id="08d1a-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="08d1a-121">不過，鑰匙鏈會自行加密。</span><span class="sxs-lookup"><span data-stu-id="08d1a-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="08d1a-122">我們已在應用程式儲存空間的所有檔案上使用 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 資料保護標號。</span><span class="sxs-lookup"><span data-stu-id="08d1a-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="08d1a-123">這表示 App 儲存空間中的檔案會經過加密，直到使用者在裝置重新開機後第一次解除鎖定裝置。</span><span class="sxs-lookup"><span data-stu-id="08d1a-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="08d1a-124">這項資訊未加密。</span><span class="sxs-lookup"><span data-stu-id="08d1a-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="08d1a-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="08d1a-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="08d1a-126">Windows Phone 在 Windows (使用 DAPI) 資料保護 API 來保護密碼。</span><span class="sxs-lookup"><span data-stu-id="08d1a-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="08d1a-127">我相信所使用的加密方案是 AES。</span><span class="sxs-lookup"><span data-stu-id="08d1a-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="08d1a-128">Windows 不會提供我們設定金鑰大小的選項， (或配置) ，因此它是由DPAPI 提供的任何功能。</span><span class="sxs-lookup"><span data-stu-id="08d1a-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="08d1a-129">它會使用裝置 TPM 保護使用者和裝置特有的金鑰。</span><span class="sxs-lookup"><span data-stu-id="08d1a-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="08d1a-130">請注意，DPAPI 金鑰並非應用程式專用。</span><span class="sxs-lookup"><span data-stu-id="08d1a-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="08d1a-131">WP App 資料受 [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I 保護，例如 creds。</span><span class="sxs-lookup"><span data-stu-id="08d1a-131">WP App Data is protected with [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, like the creds.</span></span> <span data-ttu-id="08d1a-132">根據我們想要的詳細資料，App Data 的一些索引資訊會受 (非DPAPI) AES 加密保護，以避免資料被加密，因此我們可以在不解密的情況下進行尋找，而該金鑰則由DPAPI 保護。</span><span class="sxs-lookup"><span data-stu-id="08d1a-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="08d1a-133">如果緩存資料可以到達資料檔案夾，任何程式都可以從同一部手機讀取。</span><span class="sxs-lookup"><span data-stu-id="08d1a-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="08d1a-134">Windows 加密無法防範沙箱入侵，只會嘗試外部存取。</span><span class="sxs-lookup"><span data-stu-id="08d1a-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="08d1a-135">這項資訊未加密。</span><span class="sxs-lookup"><span data-stu-id="08d1a-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="08d1a-136">**注意：** 請參閱此 [公開檔，](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) 瞭解上述每個行動平臺提供的裝置釘釘強制執行功能</span><span class="sxs-lookup"><span data-stu-id="08d1a-136">**Note:** Please refer to [this public documentation](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="08d1a-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="08d1a-137">Related topics</span></span>
[<span data-ttu-id="08d1a-138">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="08d1a-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="08d1a-139">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="08d1a-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
