---
title: Branch Office Appliance 一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 若要編輯現有 Survivable 分支裝置或 Survivable 分支伺服器的設定，您會看到下列各節：
ms.openlocfilehash: ebc3c0d0961fd239ad2b72469b1029ac7b7274d0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820295"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Branch Office Appliance 一般設定展開工具

若要編輯現有 Survivable 分支裝置或 Survivable 分支伺服器的設定，您會看到下列各節：

- 一般設定

- 恢復設定

- 中繼伺服器設定



針對 Survivable 分支裝置或 Survivable 分支伺服器，您會看到下列各項：

## <a name="general-settings"></a>一般設定

Survivable 分支裝置或 Survivable 分支伺服器的完整功能變數名稱（FQDN）。 編輯伺服器的 FQDN 會變更此值。 您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。

您可以選擇**使用所有設定的 IP 位址**或**將服務使用方式限制為選取的 IP 位址**。如果您選擇**將服務限制為定義的 IP 位址**，您需要定義主要 IP 位址，以供伺服器用於所有通訊 (公用交換電話網路 (PSTN) 閘道除外)。您必須定義個別的 IP 位址供 PSTN 使用。

在 [關聯] **** 中，您可以編輯或指定下列項目：

- [關聯存檔伺服器] 可讓您選取將封存伺服器與 Survivable 分支裝置或 Survivable 分支伺服器進行關聯。 您可以從下拉式清單中選取伺服器來選取已定義的存檔伺服器，或按一下 [**新增**] 以指定新的存檔伺服器。

    > [!IMPORTANT]
    > 您所指定的伺服器必須存在並加入網域中，您才能發行新定義的拓撲。

- [關聯監視伺服器] 可讓您選取將監視伺服器與 Survivable 分支裝置或 Survivable 分支伺服器進行關聯。 您可以從下拉式清單中選取伺服器來選取已定義的監視伺服器，或按一下 [**新增**] 以指定新的監視伺服器。

- [關聯邊緣池] 可讓您選取將 Edge 伺服器或池與 Survivable 分支裝置或 Survivable 分支伺服器進行關聯。 您可以從下拉式清單中選取伺服器，以選取已定義的 Edge Server 或集區，或按下 [新增]**** 以指定新的 Edge Server 或集區。

## <a name="resiliency"></a>恢復

恢復功能提供登錄器集區的高可用性。藉由提供備份登錄器，如果主要登錄器失敗，則備份登錄器可以接管失敗的登錄器，讓使用者能夠進行登入和通訊。視無法使用主要登錄器的系統為何而定，使用者可用的功能可能會減少。

從下拉式清單中，選取要充當 Survivable 分支裝置或 Survivable 分支伺服器之備份註冊機構的企業版前端池或標準版前端伺服器。 您也可以選擇啟用「容錯移轉」與「容錯回復」時間間隔。 啟用容錯移轉與容錯回復時間設定 (以秒為單位來指定) 可自動偵測失敗的登錄器，並且有容錯回復時間可自動判定主要登錄器是否已備份且可接管登錄器程序。

> [!IMPORTANT]
> 定義失敗偵測和容錯回復間隔時，請小心不要讓輸入的間隔導致在登錄器短時間無法回應時，發生容錯移轉和容錯回復。 根據集區或伺服器的載入情形，主要登錄器可能會在短時間內無法回應。 Survivable 分支裝置或網站中 Survivable 分支伺服器的預設值為 [池] 或 [標準版版本前端120伺服器]，用於容錯移轉和240秒以進行回退。

## <a name="mediation-server"></a>中繼伺服器

若是**中繼伺服器**，您可以指定下列內容：

**已啟用 Collocated 中繼伺服器**的核取方塊無法在 Survivable 分支裝置或 Survivable 分支伺服器上使用，因為轉送伺服器是 Collocated。

您需要在集區伺服器上定義傳輸層安全性 (TLS) 的聆聽連接埠。 此連接埠預設為 5067。 如果您選取 [啟用 TCP 連接埠]****，則必須為組合的中繼伺服器定義 TCP 連接埠。 這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。 依預設，TCP 連接埠的值為 5068。

您可以定義與 collocated 中繼伺服器相關聯的 PSTN 閘道。 如果您已定義閘道，就可以將它們與中繼伺服器建立關聯。 如果尚未定義任何閘道，但您有可以定義的閘道，則可以選取 [新增]****。 您也可以移除已針對此轉送伺服器設定的閘道。 選取閘道，然後按一下 [移除]****。

如果您有多個與中繼伺服器關聯的閘道，第一個關聯的閘道就會是預設閘道。 如果您必須選擇另一個閘道作為預設閘道，請選取您要設為預設的閘道，然後按下 [成為預設]****。

## <a name="see-also"></a>另請參閱

如需有關定義及設定 Survivable 分支裝置或 Survivable 分支伺服器設定的詳細資訊，請參閱[分支網站復原解決方案](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)。


