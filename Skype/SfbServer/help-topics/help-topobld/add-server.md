---
title: 新增伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 若要將新的伺服器新增至下列其中一種伺服器的現有集區：
ms.openlocfilehash: e40cf71b0ab52e66a3a28e0362de4f9106ddd831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818623"
---
# <a name="add-server"></a>新增伺服器
 
若要將新的伺服器新增至下列其中一種伺服器的現有集區：
  
- Enterprise Edition 前端伺服器
    
- Director 伺服器
    
- 中繼伺服器
    
- 音訊/視訊會議伺服器
    
- 信任的應用程式伺服器
    
每個新的集區伺服器各有不同的需求。在下列各節中，尋找您要新增至現有集區的伺服器類型，然後提供每種伺服器類型已定義需要的資訊。提供所要求的資訊來定義新的集區伺服器。
  
 **Enterprise Edition 前端伺服器**
  
- 新伺服器的完整網域名稱 (FQDN) (如網域名稱系統 (DNS) 中所定義)。
    
- 選取 **[使用所有設定的 IP 位址]**，表示可以使用電腦上定義的任何 IP 位址。或者，您也可以選取 **[將服務使用方式限制為選取的 IP 位址]**，然後輸入新伺服器上的特定位址。對於託管式服務，所輸入的 IP 位址會是唯一回應的 IP 位址。
    
- 當中繼伺服器是組合在前端伺服器上時，定義 [PSTN IP 位址]。
    
- 選取 [啟用 IPv6] 為此伺服器啟用 IPv6。
    
  **Director 伺服器**
  
- 新伺服器的 FQDN (如 DNS 中所定義)。
    
- 選取 [使用所有設定的 IP 位址]，表示會使用電腦上定義的任何 IP 位址。或者，您也可以選取 [將服務使用方式限制為選取的 IP 位址]，然後輸入新伺服器上的特定 IP 位址。對於託管式服務，所輸入的 IP 位址會是唯一回應的 IP 位址。
    
  **中繼伺服器**
  
- 新伺服器的 FQDN (如 DNS 中所定義)。
    
- 選取 **[使用所有設定的 IP 位址]**，表示可以使用電腦上定義的任何 IP 位址。或者，您也可以選取 **[將服務使用方式限制為選取的 IP 位址]**，並輸入新伺服器上的特定 IP 位址作為主要 IP 位址，然後輸入 IP 位址作為公用交換電話網路 (PSTN) IP 位址。對於指定的服務，所輸入的 IP 位址是唯一會回應的 IP 位址。
    
    > [!NOTE]
    > 若為中繼伺服器，根據預設，輸入作為主要 IP 位址和 PSTN IP 位址的 IP 位址相同。如果您使用專用網路介面，或使用同一網路介面上的不同 IP 位址，則可以分開定義 IP 位址。如果您有兩個網路介面，一個用於區域網路連線，另一個用於 PSTN 連線，您必須指派不同的 IP 位址。 
  
  **音訊/視訊會議伺服器**
  
- 新伺服器的 FQDN (如 DNS 中所定義)。
    
- 選取 [使用所有設定的 IP 位址]，表示可以使用電腦上定義的任何 IP 位址。或者，您也可以選取 [將服務使用方式限制為選取的 IP 位址]，然後輸入新伺服器上的特定位址。對於託管式服務，所輸入的 IP 位址會是唯一回應的 IP 位址。
    
  **信任的應用程式伺服器**
  
- 新伺服器的 FQDN (如 DNS 中所定義)。
    

