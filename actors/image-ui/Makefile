# Makefile for ml_image_ui

PROJECT  = ml_image_ui
VERSION  = $(shell cargo metadata --no-deps --format-version 1 | jq -r '.packages[] .version' | head -1)
REVISION = 0
# list of all contract claims for actor signing (space-separated)
CLAIMS   = wasmcloud:httpserver
# registry url for our actor
REG_URL  = 127.0.0.1:5000/v2/$(PROJECT):$(VERSION)
# command to upload to registry (without last wasm parameter)
PUSH_REG_CMD = wash reg push --insecure $(REG_URL)
INSECURE_FLAG=--insecure

# friendly name for the actor
ACTOR_NAME = "image-ui"
# optional call alias for actor
# ACTOR_ALIAS=nickname

include ./actor.mk

test::
	cargo clippy --all-features --all-targets
