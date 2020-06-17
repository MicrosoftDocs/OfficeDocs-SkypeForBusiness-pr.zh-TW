---
title: 防止服務的工作階段
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用舊版安裝控制台，以防止在特定電腦上執行的所有舊版服務的新會話，或阻止特定舊版服務的新會話。
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752285"
---
# <a name="prevent-sessions-for-services"></a>防止服務的工作階段

您可以使用舊版安裝控制台，以防止在特定電腦上執行的所有舊版服務的新會話，或阻止特定舊版服務的新會話。
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a>若要防止電腦上的服務的新會話

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶（或具有同等的使用者權限），或是指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 2019 的網路中的任何電腦。
    
2. 開啟商務用 Skype 控制台。
    
3. 在左導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
    
4. 在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。 
    
5. 按一下 **[動作]**。
    
6. 按一下 **[阻止對所有服務的新工作階段]**。
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服務的新工作階段

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶（或具有同等的使用者權限），或是指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 2019 的網路中的任何電腦。
    
2. 開啟商務用 Skype 控制台。
    
3. 在左導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。
    
4. 在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。 
    
5. 按一下 **[內容]**。
    
6. 視需要排序服務清單，然後按一下要阻止新工作階段的服務。
    
7. 按一下 **[動作]**。
    
8. 按一下 **[阻止對服務的新工作階段]**。
    
9. 按一下 **[關閉]**。
    

