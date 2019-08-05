---
title: 啟用及停用媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用本文中的程式, 可以使用商務用 Skype Server 的 [控制台] 來啟用或停用媒體旁路。
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188602"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用和停用媒體旁路

使用本文中的程式, 可以使用商務用 Skype Server 的 [控制台] 來啟用或停用媒體旁路。

## <a name="enable-network-media-bypass"></a>啟用網路媒體旁路 

在商務用 Skype Server 部署中, 媒體旁路設定會全域運用。 [旁路媒體] 允許呼叫繞過中繼伺服器。 如需有關何時使用媒體旁路的詳細資料, 請參閱[規劃媒體略過](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。

您可以從商務用 Skype Server 的 [控制台] 啟用和設定 [媒體旁路]。


### <a name="to-enable-and-configure-media-bypass"></a>啟用和設定媒體旁路

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**全域**]。

4.  在 [**全域**] 頁面上, 按一下 [**全域**配置]。 永遠只有一個設定, 且永遠會將它命名為 Global。

5.  按一下 [**編輯**] 功能表上的 [**查看詳細資料**]。

6.  在 [**編輯全域設定**] 頁面上, 按一下 [**啟用旁路媒體**] 核取方塊。

7.  選取下列其中一個選項:
    
      - **[永遠略過**   ] 選取此選項, 即可在所有通話中嘗試媒體旁路。 如果啟用 [通話許可控制 (CAC)], 此選項將無法使用。 如果未啟用 CAC, 請在下列情況下選取此選項:
        
          - 您不需要頻寬控制。
        
          - 不需要精確的設定來判斷何時應發生旁路。
        
          - 閘道與用戶端之間有完整的連線能力。
    
      - **** 如果啟用了 CAC, 請使用網站和地區設定, 預設會選取此選項, 且無法進行變更。    選取此選項時, 系統會使用網路設定網站和區域來判斷何時可能會略過媒體。 如果您選取此選項, 您可以選擇針對未對應的網站啟用 [旁路]。 只有當您有一個或多個大型網站與不含頻寬限制 (例如大型中央網站) 的同一個區域相關聯時, 請按一下 [**啟用旁路未對應的網站**] 核取方塊, 而且還有一些與您相關聯的分支網站具有頻寬限制的同一個區域。 當您針對未對應的網站啟用 [旁路] 時, 系統會簡化配置, 因為您只需指定與分支網站相關聯的子網, 而不需要指定所有與所有網站相關聯的子網。 如果啟用 CAC, 我們建議您不要選取 [**啟用旁路未對應的網站**] 核取方塊。

8.  按一下 [**認可**], 儲存您的變更。


## <a name="disable-network-media-bypass"></a>停用網路媒體旁路

在商務用 Skype Server 部署中, 媒體旁路設定會全域運用。 [旁路媒體] 允許呼叫繞過中繼伺服器。 如需有關何時使用媒體旁路的詳細資料, 請參閱[規劃媒體略過](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。 您可以從商務用 Skype Server 的 [控制台] 停用 [媒體旁路]。 


### <a name="to-disable-media-bypass"></a>停用媒體旁路

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 

3.  在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**全域**]。

4.  在 [**全域**] 頁面上, 按一下 [**全域**配置]。 永遠只有一個設定, 且永遠會將它命名為 Global。

5.  按一下 [**編輯**] 功能表上的 [**查看詳細資料**]。

6.  在 [**編輯全域設定**] 頁面上, 清除 [**啟用媒體旁路**] 核取方塊。

7.  按一下 [**認可**], 儲存您的變更。

  
