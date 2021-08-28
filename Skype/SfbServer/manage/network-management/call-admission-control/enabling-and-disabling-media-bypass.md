---
title: 啟用和停用媒體旁路
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 使用本文中的程式，透過「商務用 Skype Server 控制台」來啟用或停用媒體旁路。
ms.openlocfilehash: 6881b1627cf648cc948b5e8b3564fa3b12caa183
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604814"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用及停用媒體旁路

使用本文中的程式，透過「商務用 Skype Server 控制台」來啟用或停用媒體旁路。

## <a name="enable-network-media-bypass"></a>啟用網路媒體旁路 

媒體旁路設定會在整個商務用 Skype Server 部署中全域套用。 媒體旁路允許來電略過轉送伺服器。 如需有關何時使用媒體旁路的詳細資訊，請參閱 [Plan for media 旁路](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。

您可以從商務用 Skype Server 控制台啟用及設定媒體旁路。


### <a name="to-enable-and-configure-media-bypass"></a>啟用及設定媒體旁路

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **通用**]。

4.  在 **[全域]** 頁面上，按一下 **[全域]** 設定。 永遠只有一個設定，而且永遠稱為 Global。

5.  在 [ **編輯** ] 功能表上，按一下 [ **查看詳細資料**]。

6.  在 [ **編輯通用設定** ] 頁面上，按一下 [ **啟用媒體旁路** ] 核取方塊。

7.  選取下列其中一個選項：
    
      - **永遠略過**   選取此選項，可在所有呼叫時嘗試媒體旁路。 如果已啟用 (CAC) 的通話許可控制，此選項將無法使用。 如果未啟用 CAC，請在下列情況下選取此選項：
        
          - 不需要頻寬控制。
        
          - 不需要微調設定，就能決定何時應該應該發生旁路。
        
          - 閘道和用戶端之間有完整的連線能力。
    
      - **使用網站與地區**   設定  如果啟用 CAC，預設會選取此選項，而且無法變更。 選取此選項時，會使用網路設定網站和區域來決定何時可以進行媒體旁路。 如果您選取此選項，您可以針對未對應的網站，選擇啟用旁路。 只有當您有一個或多個大型網站與沒有頻寬限制的相同區域相關聯時，才會按一下 [為 **未對應的網站啟用旁路** ] 核取方塊 (例如，大型中央網站) ，而且您也有一些分支網站與具有頻寬限制的相同地區相關聯。 當您為未對應的網站啟用旁路時，將會簡化設定，因為您只會指定與分支網站相關聯的子網，而不需要指定所有網站相關聯的所有子網。 如果啟用 CAC，建議您不要選取 [為 **未對應的網站啟用旁路** ] 核取方塊。

8.  按一下 [ **認可** ] 以儲存變更。


## <a name="disable-network-media-bypass"></a>停用網路媒體旁路

媒體旁路設定會在整個商務用 Skype Server 部署中全域套用。 媒體旁路允許來電略過轉送伺服器。 如需有關何時使用媒體旁路的詳細資訊，請參閱 [Plan for media 旁路](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。 您可以從商務用 Skype Server 控制台停用媒體旁路。 


### <a name="to-disable-media-bypass"></a>停用媒體旁路

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **通用**]。

4.  在 **[全域]** 頁面上，按一下 **[全域]** 設定。 永遠只有一個設定，而且永遠稱為 Global。

5.  在 [ **編輯** ] 功能表上，按一下 [ **查看詳細資料**]。

6.  在 [ **編輯通用設定** ] 頁面上，清除 [ **啟用媒體旁路** ] 核取方塊。

7.  按一下 [ **認可** ] 以儲存變更。

  
