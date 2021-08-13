---
title: 自訂通話駐留 inSkype for Business 的等候音樂
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 在商務用 Skype Server 企業語音中自訂通話駐留的等候音樂。
ms.openlocfilehash: 6dc080071df29e12a979e2591a73c02439a0a6271cda45b4105a009d1c70e307
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323535"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>自訂通話駐留 inSkype for Business 的等候音樂
 
在商務用 Skype Server 企業語音中自訂通話駐留的等候音樂。
  
您可以指定自己的音樂檔案，以用於等候音樂，而不是隨商務用 Skype Server 附帶的預設音樂檔。 如要自訂等候音樂，請使用 **Set-CsCallParkServiceMusicOnHoldFile** Cmdlet。
  
> [!NOTE]
> 如果您自訂等候音樂，且想要將相同的音樂用於多個網站，則必須為每個執行通話駐留應用程式的網站設定音樂檔。 
  
### <a name="to-customize-the-music-file"></a>自訂音樂檔案

1. 以 **委派安裝許可權** 中所述，以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 運行：
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > 使用 **Get-CsService** Cmdlet 來識別服務。 如需詳細資訊，請參閱 [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)。 
  
    下列範例顯示如何取得檔案 soothingmusic.wma 的位元組陣列內容，並將其指派給變數。 然後將音訊檔案指派為通話駐留時的等候音樂檔案。 如需詳細資訊，請參閱 [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>另請參閱

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)