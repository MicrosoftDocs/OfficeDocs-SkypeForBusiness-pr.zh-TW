---
title: Director 一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 若要編輯現有主管的設定，您會看到下列各節：
ms.openlocfilehash: e6fb587484cd4024e69c8630e49f95a978ec747a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820125"
---
# <a name="director-general-settings-expander"></a>Director 一般設定展開工具
 
若要編輯現有主管的設定，您會看到下列各節：
  
- 一般設定
    
- Web 服務
    


## <a name="general-settings"></a>一般設定

主管池的完整功能變數名稱（FQDN）。 編輯伺服器的 FQDN 會變更此值。 您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。
  
在 [關聯]**** 中，您可以編輯或指定下列項目：
  
要使用之主管池的檔案共用。 選取已在拓撲建立器中定義的現有檔案共用，或按一下 [**新增**] 以建立新的檔案共用定義。
  
[監視 SQL Server store]。
  
> [!IMPORTANT]
> 您所指定的伺服器必須存在並加入網域中，您才能發行新定義的拓撲。 如果您已建立新的檔案共用，則必須在您指派的伺服器上建立檔案共用。 
  
## <a name="web-services"></a>Web 服務

若要在主管池上編輯或指定 Web 服務的其他設定，您可以在內部 Web 服務和外部 Web 服務中修改或指定設定。
  
對於**內部 web 服務**，您可以指定下列專案：
  
> [!CAUTION]
> 如果您有多個前端池或前端伺服器，外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為**pool01.contoso.com**，則無法將**pool01.contoso.com**用於另一個前端池或前端伺服器。 如果您也要部署控制器，則為任何主管或主管池定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。 如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須是與任何其他的前端池、控制器或主管池都是唯一的。
  
如果您選取 [覆寫 FQDN]，您可以為集區上的 [內部 Web] 服務識別指定不同的 FQDN。 根據預設，設定是針對主管池所定義的目前的 [池名稱]。
  
您可以為您的部署所需的 HTTP 和 HTTPS 指定偵聽與已發佈埠。 HTTPS 的埠80和 HTTPS 的埠443預設設定是最常見的設定，除非您在組織和基礎結構設計中有特定需求，否則通常不需要加以變更。
  
針對**外部 web 服務**，您可以指定下列專案：
  
您可以定義外部 Web 服務的 FQDN。 此處指定的 FQDN 通常會依您外部連線的需求 (例如反向 Proxy) 而定義。
  
您可以為您的部署所需的 HTTP 和 HTTPS 指定偵聽與已發佈埠。 HTTPS 的埠8080的預設設定與 HTTPS 的埠4443最初定義。 您可以根據您反向 Proxy 與外部網路的需求，為聆聽連接埠變更這些設定。 已發佈的埠會設定為 HTTP 的埠80，以及 HTTPS 的埠443的預設值。 這些值決定控制器池或控制器伺服器將接聽傳入要求的埠。 通常不需要變更這些功能，除非在該池中有埠需求衝突。 需要使用相同埠值的內部和外部發佈埠。 這不是衝突。
  

