
Min and max, founded to a given decimal
`getmin <- function(x) { plyr::round_any(min(x), 0.05, f=floor) }`
`getmax <- function(x) { plyr::round_any(max(x), 0.05, f=ceiling) }`

Gamma mean
`gm_meansd_to_shaperate <- function(meansd) <- { c(meansd[1]/meansd[2])^2, meansd[1]/(meansd[2]^2) }`
