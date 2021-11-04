---
title: Director 一般設定展開工具
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 若要編輯現有 Director 的設定，您會看到下列區段：
ms.openlocfilehash: 610145333ade88f6f190905cf1c263cea0025a44
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773893"
---
# <a name="director-general-settings-expander"></a>Director 一般設定展開工具
 
若要編輯現有 Director 的設定，您會看到下列區段：
  
- 一般設定
    
- Web 服務
    


## <a name="general-settings"></a>一般設定

Director 集區 (FQDN) 的完整功能變數名稱。 編輯伺服器的 FQDN 會變更此值。 您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。
  
在 [ **關聯** ] 中，您可以編輯或指定下列專案：
  
要使用之 Director 集區的檔案共用。 選取拓撲產生器中已定義的現有檔共用，或按一下 [ **新增** ] 建立新的檔案共用定義。
  
監視 SQL Server 儲存區。
  
> [!IMPORTANT]
> 在發佈新定義的拓撲之前，您指定的伺服器必須存在並加入網域中。 如果您已建立新的檔案共用，必須在您指派的伺服器上建立檔案共用。 
  
## <a name="web-services"></a>Web 服務

若要針對 Director 集區上的 Web 服務編輯或指定其他設定，請修改或指定 [內部 Web 服務] 與 [外部 Web 服務] 中的設定。
  
針對 [ **內部 web 服務** ]，您可以指定下列專案：
  
> [!CAUTION]
> 如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。 例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 **pool01.contoso.com**，則無法將 **pool01.contoso.com** 用於另一個前端集區或前端伺服器。 如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。 如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。
  
如果您選取 [覆寫 FQDN]，您可以為集區上的內部 Web 服務識別指定不同的 FQDN。 根據預設，設定為 Director 集區所定義的目前集區名稱。
  
您可以為您的部署所需的 HTTP 和 HTTPS 指定聽取和發行的埠。 HTTPS 的埠80的預設設定和 HTTPS 的埠443是最常見的設定，除非您在組織和基礎結構設計中有特定需求，否則通常不需要加以變更。
  
針對 [ **外部 web 服務**]，您可以指定下列專案：
  
您可以定義外部 Web 服務的 FQDN。 在這裡指定的 FQDN 通常會由外部連線需求（例如反向 proxy）的需求所定義。
  
您可以為您的部署所需的 HTTP 和 HTTPS 指定聽取和發行的埠。 HTTPS 的埠8080的預設設定會先定義 HTTPS 的埠4443。 您可以根據您的反向 proxy 和外部網路需求的需求，來變更聆聽埠的這些設定。 已發佈的埠設定為埠80的預設值，HTTP 及埠443用於 HTTPS。 這些值會決定 Director 集區或 Director 伺服器將接聽傳入要求的埠。 除非集區的埠需求有衝突，否則通常不需要變更這些功能。 期望使用相同埠值的內部及外部發佈埠。 這不是衝突。
  

