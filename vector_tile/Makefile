fetch:
	git clone https://github.com/globalmaps/gmlk20.git

convert:
	cd gmlk20; \
	ogr2ogr airp_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 airp_lka.shp; \
	ogr2ogr builtupp_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 builtupp_lka.shp; \
	ogr2ogr coastl_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 coastl_lka.shp; \
	ogr2ogr inwatera_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 inwatera_lka.shp; \
	ogr2ogr polbnda_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 polbnda_lka.shp; \
	ogr2ogr polbndl_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 polbndl_lka.shp; \
	ogr2ogr raill_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 raill_lka.shp; \
	ogr2ogr riverl_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 riverl_lka.shp; \
	ogr2ogr roadl_lka.geojson -s_srs EPSG:4326 -t_srs EPSG:4326 roadl_lka.shp

generate:
	tippecanoe -o lka.pmtiles \
	  -L airp:gmlk20/airp_lka.geojson \
	  -L builtupp:gmlk20/builtupp_lka.geojson \
	  -L coastl:gmlk20/coastl_lka.geojson \
	  -L inwatera:gmlk20/inwatera_lka.geojson \
	  -L polbnda:gmlk20/polbnda_lka.geojson \
	  -L polbndl:gmlk20/polbndl_lka.geojson \
	  -L raill:gmlk20/raill_lka.geojson \
	  -L riverl:gmlk20/riverl_lka.geojson \
	  -L roadl:gmlk20/roadl_lka.geojson

tileserver-gl:
	docker run --rm -it -v $(PWD):/data -p 8080:80 \
	  maptiler/tileserver-gl-light \
	  -p 80 --file /data/lka.mbtiles

serve:
	docker run -p 8000:80 -v $(PWD):/usr/share/nginx/html:ro nginx

practice:
	charites serve style-practice.yml

build:
	charites build style-practice.yml style-practice.json

build-ipfs:
	charites build style-ipfs.yml style-ipfs.json

ipfs:
	ipfs add lka.pmtiles
