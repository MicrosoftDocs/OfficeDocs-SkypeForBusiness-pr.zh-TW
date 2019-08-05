---
title: 在商務用 inSkype 上自訂通話寄存音樂
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 在商務用 Skype Server Enterprise Voice 中, 自訂通話寄存音樂以進行封存。
ms.openlocfilehash: 4111bcc42a3820e3957f526e360264aa7d098d05
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190408"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>在商務用 inSkype 上自訂通話寄存音樂
 
在商務用 Skype Server Enterprise Voice 中, 自訂通話寄存音樂以進行封存。
  
您可以指定自己的音樂檔案以供等候音樂使用, 而不是隨商務用 Skype 伺服器隨附的預設音樂檔案。 若要在保留時自訂音樂, 請使用**CsCallParkServiceMusicOnHoldFile** Cmdlet。
  
> [!NOTE]
> 如果您自訂 [等候音樂] 並想要在多個網站上擁有相同的音樂, 您必須針對每個執行通話駐留應用程式的網站設定音樂檔案。 
  
### <a name="to-customize-the-music-file"></a>自訂音樂檔案

1. 登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝, 如**委派設定許可權**中所述。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. 用盡
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > 使用**CsService** Cmdlet 來識別服務。 如需詳細資訊, 請參閱[CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。 
  
    下列範例顯示如何取得檔案的內容 (soothingmusic) 作為位元組陣列, 並將它指派給變數。 然後, 音訊檔案會指派為 [通話駐留] 的 [音樂保留] 檔案。 如需詳細資訊, 請參閱[設定 CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>另請參閱

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
