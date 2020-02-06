---
title: 新增伺服器​​
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 若要將新的伺服器新增至現有的伺服器池中，請在池中是下列其中一項：
ms.openlocfilehash: c3593835fa1204b5ed4e74729a7ec369069e04f8
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798500"
---
# <a name="add-server"></a>新增伺服器​​
 
若要將新的伺服器新增至現有的伺服器池中，請在池中是下列其中一項：
  
- 企業版前端伺服器
    
- 控制器伺服器
    
- 中繼伺服器
    
- 音訊/視訊會議伺服器
    
- 受信任的應用程式伺服器
    
每個新的 [池伺服器] 都有不同的需求。 在下列各節中，找出您要新增到現有區的伺服器類型，並提供所需的資訊，並為每個伺服器類型定義。 您提供要求的資訊來定義新的 pool 伺服器。
  
 **企業版前端伺服器**
  
- 在網域名稱系統（DNS）中定義之新伺服器的完整功能變數名稱（FQDN）。
    
- 選取 [**使用所有已設定的 ip 位址**]，這表示電腦上定義的任何 ip 位址都可以使用。 或者，您也可以選取 [**將服務使用限制為選取的 IP 位址**]，並在新伺服器上輸入特定的位址。 輸入的 IP 位址是唯一將回應託管服務的 IP 位址。
    
- 在前端伺服器上 collocated 轉送伺服器時，定義**PSTN IP 位址**。
    
- 選取 [**啟用 ipv6** ]，為此伺服器啟用 ipv6。
    
  **控制器伺服器**
  
- 在 DNS 中定義的新伺服器 FQDN。
    
- 選取 [**使用所有已設定的 ip 位址**]，表示將會使用電腦上定義的任何 ip 位址。 或者，您也可以選取 [**將服務使用限制為選取的 IP 位址**]，並在新伺服器上輸入特定的 ip 位址。 輸入的 IP 位址是唯一將回應託管服務的 IP 位址。
    
  **中繼伺服器**
  
- 在 DNS 中定義的新伺服器 FQDN。
    
- 選取 [**使用所有已設定的 ip 位址**]，這表示電腦上定義的任何 ip 位址都可以使用。 或者，您也可以選取 [**將服務使用限制為選取的 IP 位址**]，並在新伺服器上輸入特定的 ip 位址作為主要 ip 位址，並輸入公用交換電話網絡（PSTN） ip 位址的 ip 位址。 輸入的 IP 位址是唯一將回應指定服務的 IP 位址。
    
    > [!NOTE]
    > 在中繼伺服器中，為主要 IP 位址和 PSTN IP 位址輸入的 IP 位址，預設是相同的。 如果您使用的是專用的網路介面，或在相同的網路介面上單獨的 IP 位址，就可以單獨定義 IP 位址。 如果您有兩個網路介面，一個適用于本機網路連線，另一個用於 PSTN 連線，則必須指派不同的 IP 位址。 
  
  **音訊/視訊會議伺服器**
  
- 在 DNS 中定義的新伺服器 FQDN。
    
- 選取 [**使用所有已設定的 ip 位址**]，這表示電腦上定義的任何 ip 位址都可以使用。 或者，您也可以選取 [**將服務使用限制為選取的 IP 位址**]，並在新伺服器上輸入特定的位址。 輸入的 IP 位址是唯一將回應託管服務的 IP 位址。
    
  **受信任的應用程式伺服器**
  
- 在 DNS 中定義的新伺服器 FQDN。
    

