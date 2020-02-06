---
title: 新增 Edge 電腦內部 IP 2010
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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 使用此頁面來指定內部 IP 位址，以及邊緣伺服器的內部完整功能變數名稱（FQDN）。
ms.openlocfilehash: 1847362f93c1d1ff67c09fb9f552641b0e770bbc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821135"
---
# <a name="add-edge-machine-internal-ip-2010"></a>新增 Edge 電腦內部 IP 2010

使用此頁面來指定內部 IP 位址，以及邊緣伺服器的內部完整功能變數名稱（FQDN）。

- 在 [**內部 IPv4 位址**] 中，輸入您要新增至池中的邊緣伺服器 IP 位址。

- 在**內部 FQDN**中，輸入您要新增至池中的邊緣伺服器的完整功能變數名稱（FQDN）。

您指定的 FQDN 必須與伺服器上設定的電腦名稱稱相同。 根據預設，未加入網域之電腦的電腦名稱是簡稱，不是 FQDN。 拓撲產生器會使用 FQDN，而非簡稱。 因此，您必須在要部署成邊緣伺服器且未加入網域的電腦名稱稱上設定網域名稱系統（DNS）尾碼。 如需新增 DNS 尾碼至電腦名稱稱的詳細資料，請參閱[設定 dns 以取得 Edge 支援](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


