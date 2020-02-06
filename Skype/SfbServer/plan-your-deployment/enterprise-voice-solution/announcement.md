---
title: 規劃商務用 Skype 中的宣告應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 規劃商務用 Skype Server Enterprise Voice 中的宣告應用程式，在您的組織中設定電話撥出未指派電話號碼的方式。 包括音訊檔需求。
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803263"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>規劃商務用 Skype 中的宣告應用程式

規劃商務用 Skype Server Enterprise Voice 中的宣告應用程式，在您的組織中設定電話撥出未指派電話號碼的方式。 包括音訊檔需求。

商務用 Skype Server 宣告應用程式可讓您設定撥入電話號碼對您的組織有效，但不會指派給使用者或電話。 您可以將這些來電轉接至預先定義的目的地（電話號碼、SIP URI 或語音信箱），或播放音訊公告或兩者。 宣告應用程式可協助您避免來電者 misdials 和聽到忙音或 SIP 用戶端收到錯誤訊息的情況。 本節包含宣告應用程式專用的規劃資訊

當您部署宣告應用程式時，您必須設定 [未指定的數位] 資料表，決定當有人撥打未指派的號碼時所採取的動作。 [未指定的數位] 表格包含適用于組織的電話號碼範圍，並指定哪個宣告應用程式會處理每個範圍。 當來電者撥打電話給您的組織而言，但不是指派給任何人時，商務用 Skype 伺服器會在未指定的數位路由表中尋找該號碼，找出該數位的範圍，並將呼叫路由到為該範圍指定的宣告應用程式。 [宣告] 應用程式會應答通話並播放音訊訊息（如果您將它設定為這樣做），然後中斷通話，或將它轉移至預先確定的目的地，例如操作員。 您可以使用商務用 Skype Server Management Shell Cmdlet 來設定多個音訊訊息或傳輸目的地。

設定未指派號碼表的方式取決於其使用方式。 如果您的特定號碼已不再使用，而您想要播放專為每個數位提供的訊息，您可以在 [未指定的數位] 資料表中輸入那些特定的數位。 例如，如果您變更了客戶服務服務台的號碼，您可以輸入舊的客戶服務號碼，並將其與提供新號碼的公告建立關聯。 如果您想要在呼叫未獲指派之號碼的任何人（例如，針對離開貴組織的員工）發出一般訊息，您可以為組織中的所有有效延伸輸入範圍。 每當來電者撥打目前未指派的號碼時，就會呼叫 [未指定的數位] 資料表。

## <a name="deployment-and-requirements"></a>部署與需求

宣告應用程式會自動與回應群組應用程式一起安裝。 宣告與回應群組應用程式是企業語音部署的標準元件：當您部署企業語音時，這兩個應用程式都會自動部署。

### <a name="software-requirements"></a>軟體需求

執行宣告應用程式的所有前端伺服器或標準版伺服器，都必須針對執行 Windows Server 2008 R2 的伺服器安裝 windows Media 格式執行時間，或是執行 Windows Server 2012 的伺服器的 Microsoft Media Foundation，或Windows Server 2012 R2。 針對 Windows Server 2008 R2，Windows Media 格式執行時間會安裝為 Windows 桌面體驗的一部分。 Windows Media 格式執行時間或 Microsoft 媒體基礎是 Windows Media 音訊（.wma）檔案所必需的，這些檔案是宣告應用程式在公告和音樂中播放的檔。

### <a name="port-requirements"></a>埠需求

宣告應用程式使用**埠 5071**進行 SIP 偵聽要求。

> [!NOTE]
> 這個埠是預設設定，您可以使用**CsApplicationServer** Cmdlet 進行變更。 如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。

### <a name="audio-file-requirements"></a>音訊檔需求

宣告應用程式支援 Wave （.wav）檔案格式和 Windows Media 音訊（.wma）檔案格式，以供音樂和公告用。 宣告應用程式的音訊檔需求與回應群組應用程式相同。 如需詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。


