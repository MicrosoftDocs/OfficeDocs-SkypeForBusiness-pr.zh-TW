---
title: 啟用和停用媒體旁路
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 使用本文中的程式，使用 商務用 Skype Server 主控台啟用或停用媒體旁路。
ms.openlocfilehash: 38ec29c6e4b51a4c6898b13c4de0172f55947907
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675335"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用及停用媒體旁路

使用本文中的程式，使用 商務用 Skype Server 主控台啟用或停用媒體旁路。

## <a name="enable-network-media-bypass"></a>啟用網路媒體旁路 

媒體旁路設定會在商務用 Skype Server部署中全域套用。 媒體旁路允許呼叫略過轉送伺服器。 如需何時使用媒體旁路的詳細資訊，請參閱 [規劃媒體旁路](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。

您可以從商務用 Skype Server 主控台啟用和設定媒體旁路。


### <a name="to-enable-and-configure-media-bypass"></a>啟用和設定媒體旁路

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶， (或具有對等的使用者權限) ，或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理員 URL 以開啟商務用 Skype Server 主控台。 

3.  在左側導覽列中，按一下 [ **網路設定]**，然後按一下 [ **全域]**。

4.  在 **[全域]** 頁面上，按一下 **[全域]** 設定。 一律只有一個組態，且一律命名為全域。

5.  在 [ **編輯]** 功能表上，按一下 [ **檢視詳細資料]**。

6.  在 [ **編輯全域設定]** 頁面上，按一下 [ **啟用媒體旁路** ] 核取方塊。

7.  選取下列其中一個選項：
    
      - **永遠略過**   選取此選項可嘗試在所有呼叫上略過媒體。 如果啟用 CAC)  (通話許可控制，則無法使用此選項。 如果未啟用 CAC，請在下列情況下選取此選項：
        
          - 不需要頻寬控制。
        
          - 不需要更細緻的設定，即可判斷何時應該發生略過。
        
          - 閘道與用戶端之間有完整的連線能力。
    
      - **使用月臺和區域設定**   如果啟用 CAC，預設會選取此選項，而且無法變更。 選取此選項時，將會使用網路設定月臺和區域來判斷媒體何時可以略過。 如果您選取此選項，您可以選擇為未對應的網站啟用略過。 只有在您有一或多個與沒有頻寬條件約束的相同區域相關聯的大型網站時，才按一下 [ **啟用非** 對應網站的略過] 核取方塊 (例如，大型中央網站) ，而且您也有一些與具有頻寬條件約束的相同區域相關聯的分支網站。 當您啟用非對應月臺的略過時，設定會簡化，因為您只指定與分支月臺相關聯的子網，而不需要指定與所有月臺相關聯的所有子網。 如果已啟用 CAC，建議您不要選取 [ **啟用非對應網站的略過** ] 核取方塊。

8.  按一下 **[認可** ] 以儲存您的變更。


## <a name="disable-network-media-bypass"></a>停用網路媒體旁路

媒體旁路設定會在商務用 Skype Server部署中全域套用。 媒體旁路允許呼叫略過轉送伺服器。 如需何時使用媒體旁路的詳細資訊，請參閱 [規劃媒體旁路](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。 您可以從商務用 Skype Server 主控台停用媒體旁路。 


### <a name="to-disable-media-bypass"></a>停用媒體旁路

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶， (或具有對等的使用者權限) ，或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理員 URL 以開啟商務用 Skype Server 主控台。 

3.  在左側導覽列中，按一下 [ **網路設定]**，然後按一下 [ **全域]**。

4.  在 **[全域]** 頁面上，按一下 **[全域]** 設定。 一律只有一個組態，且一律命名為全域。

5.  在 [ **編輯]** 功能表上，按一下 [ **檢視詳細資料]**。

6.  在 [ **編輯全域設定]** 頁面上，清除 [ **啟用媒體旁路** ] 核取方塊。

7.  按一下 **[認可** ] 以儲存您的變更。

  
